- Set a new dune_build project and used [spin](https://github.com/tmattio/spin) to generate an OCaml project 
- First of all, we want to write codes for metric collection so that we could console with the UI afterwards
- Today we wrote code of modules - interface (list of functions, signatures)
- To write inside of `hello.mli` : needed to check `build-info` (dune)
  - referencing [build_info](https://github.com/ocaml/dune/blob/main/otherlibs/build-info/src/build_info.mli#L4)

- Check the TODO and see what we have to do, have done
- `uptime`: number of times that has been live in the system. number of seconds.

- In `hello.ml`, `let ocaml_version` should reference `Module Stdlib.Sys` so that `= Sys.ocaml_version` (can see from https://ocaml.org/api/Stdlib.Sys.html#:~:text=val%20ocaml_version%20%3A%20string)
- When module needs to be deconstructed like in `let (dashboard) version` in `hello.ml` -> you should write `match` — `type result (none, some)`
