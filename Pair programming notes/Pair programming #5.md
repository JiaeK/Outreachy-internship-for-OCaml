- `Event` in analytics: 
  - it is recorded when an internet user performs an action on your website 
  - Events can be measured independently of loading a new page 
  - Events in Google Analytics are user interactions on your website that cannot be tracked as page views within a session 
  - Any activity that users take on a page of your website is considered an 'event' or 'event hit'
- What is `unique visitor` different from other criteria like `top pages`: Imagine a single visitor triggering two pageviews: `/page1` and `/page2`. In this case your dashboard would show 1 unique visitor in total. However, the 'Top pages' report would show one unique visitor for `/page1` and one unique visitor for `/page2`. This happens because visitors can view more than a single page or trigger more than a single custom event on your site. 
- `assertion` is a boolean expression at a specific point in a program which will be true unless there is a bug in the program. An assertion could simply be a comment used by the programmer to think about how the code works. ... When programmers talk about assertions they usually mean this kind of executed assertion.
- `utime`: 
  - The utime() function sets the access and modification times of the file named by the path argument. If times is a null pointer, the access and modification times of `dream_dashboard.ml & .mli` files, referenced [dream-analytics](https://github.com/tmattio/dream-analytics/blob/32a3e9eb2fca3e7102ad1d87ebc617c3bd717eaf/lib/core/user_agent.ml) - implemented `ua`, `os`, `device info` 
- declared `event` inside of `dream_dashboard.ml` & implemented [`event.ml`](https://github.com/JiaeK/dream-dashboard/blob/9d3c42999828805a363a3a77c59315229f45bfff/lib/dream-analytics/event.ml)
- This 500 means HTTP's Internal Server Error
   > Error _ ->  Dream.respond ~code:500

- run ‘opam upgrade’ or ‘eval `opam config env`’ or ‘npm install’ when the project doesn’t run smoothly - perhaps we need dependencies' updates
- `?` sign means option sign, when you already defined ‘option’
- when you wrote something in ml file, you need to ALSO write inside of mli file’s router
- We wrote code for analytics but it’s empty now because there's no statistics. For that, we have to create Middleware. (we need middleware each time. each time we write middleware when we need)
- We need a middleware which inspects ua
- implemented [` @@ Dream.router`](https://github.com/JiaeK/dream-dashboard/blob/f04cf1f72438eef2891e745b1fd9cb94a67c0a75/example/server.ml#L4) in server.ml
- debugged event examples
- `store` in our codebase is storing events
- `config = Config.default` is the same with the rest of the `let config..` & this is synthetic sugar:
```
let router ?(config = Config.default) ?(prefix = "/dashboard" ) ?(middlewares = []) () =
  let config =
      match config with
      | None -> Config.default
      | Some config -> config
  in
```

