- Length of a list in OCaml:
``` 
let rec length lst =
  match lst with
  | [] -> 0
  | el :: rest -> 1 + length rest
```
is the same with `List. length` ([example](https://github.com/JiaeK/dream-dashboard/blob/bbc30370946d99aa93446766c5d882c313bc8995/src/event.ml#L51) in the dashboard)
- From `let hashtbl = Hashtbl.create 256`, the 256 is the size of hashtbl
<br>

- we wanted to localize IPs - `dbip` is a way to do it but it’ll take like 3.7GB and we don’t want that
  - DB-IP is an online geolocation IP database. Users can look up IP addresses to find out locations of the IP addresses, as well as download and access the IP database. The DB-IP API allows developers to access and integrate the functionality of DB-IP with other applications
  - suggestion: get IP -> counties (and hash those). we need to use [ocaml mmdb](https://github.com/issuu/ocaml-mmdb) - OCaml bindings to the MaxMind Geo IP database (also known as GeoIP2)
  - downloaded some dependencies to integrate `ocaml-mmdb`, and also updated Dream so in dune-project & in dream-dashboard.opam, we rewrite `(dream (>= 1.0.0~alpha3))` + `mmdb`, `digestif` (for ip using)
  - updated Dream so it changed API - meaning that Dream’s API also changed so it broke few things like `router` -> should be changed to `route` in middleware 
  - the Uri means host and the localhost8080 means no host
  - turned out `mmdb` is not that suitable since this Dream library to use binding to C library (so don’t need mmdb dependency anymore) 
  - added a file called ‘dbip_asset’ but then realized this can’t be streamed because it's too large
  - then created [`ip_info.ml`](https://github.com/JiaeK/dream-dashboard/blob/main/src/ip_info.ml) file to integrate a json file with OCaml = yojson
  - for the ip, we have to first “query” if the info we get is really ip or not — in [`let query_dbip ip =..`](https://github.com/JiaeK/dream-dashboard/blob/f04cf1f72438eef2891e745b1fd9cb94a67c0a75/src/ip_info.ml#L19)
  - the reason why we declare [`hyper`](https://github.com/JiaeK/dream-dashboard/blob/f04cf1f72438eef2891e745b1fd9cb94a67c0a75/src/ip_info.ml#L22) is because it helps us to use HTML with it
  - Reference: [How to convert JSON schema into the OCaml/ReasonML type](https://stackoverflow.com/questions/60718364/how-to-convert-json-schema-into-the-ocaml-reasonml-type)
  - [Yojson](https://github.com/ocaml-community/yojson): JSON library for OCaml. This library parses JSON data into a nested OCaml tree data structure
  - needed to decode yojson -> decided to use [ppx_deriving for json](https://github.com/ocaml-ppx/ppx_deriving_yojson) => [@@deriving yojson] (generate code for decode) 
  - set the queries 1000 per a day
  - bind and match is the same thing but bind is more compact
  - changed `ssl` to `hyper` and that makes some clashes, one of which is https should change to http
  - SSL (Secure Sockets Layer): SSL is a secure protocol that works on the top of HTTP to provide security
  - then the query was failing so thought maybe bc of the header so we put `user-agent`, `hyper`
  




