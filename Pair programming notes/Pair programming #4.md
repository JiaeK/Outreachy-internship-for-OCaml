-  we need `match Sys.os_type with` + `"Unix"   | "Win32" | "Cygwin"...`
   - for this, we need [`luv`](https://github.com/aantron/luv) - opam install `luv` + write down 'luv' inside of dune project
- changed `os_type` to `platform` - using ocaml-node’s [os.ml](https://github.com/tmattio/ocaml-node/blob/6913461fb7cde73a7963ced5d26878a9b1f6ac03/ocaml-node-unix/lib/os.ml#L33)
- reference for os: [opamrepositoryconfig.ml](https://github.com/ocaml/opam/blob/3cd0829538b90191bcd1c4eaa76c00d3d987b4ea/src/repository/opamRepositoryConfig.ml#L51)
- we'll use `luv` also for `CPU` - luv’s [system_info.ml](https://github.com/aantron/luv/blob/master/src/system_info.ml)
- ran `make` to find the type
- referenced `ocaml-node-unix` from [process.ml](https://github.com/tmattio/ocaml-node/blob/6913461fb7cde73a7963ced5d26878a9b1f6ac03/ocaml-node-unix/lib/process.ml)
- [ocaml-node](https://github.com/tmattio/ocaml-node/tree/6913461fb7cde73a7963ced5d26878a9b1f6ac03) is like node.js - it makes JS can use backend stuff and the terminal looks like JS too. The goal of the project is to implement node.js’ API in ocaml
- for architecture: 
  - we call it as `arch` 
  - the reason why we put `arch_string` too is because in type arch, if we need to use in HTML (in index_template), we have to declare string to understand/connect to html
- `platform_string` is also for the same reason and that’s for `os_type` and this would be better when it looks like Phoenix’ ‘system information’
- need to rewrite code for `uptime`
- we tried to implement code for `Total input` & `output` for `I/O` but the outcome was not satisfying:
  - for I/O we need middleware
  - checked `Dream`'s [`content_length`](https://github.com/aantron/dream/blob/acc2a1695effa5810a32bc3c0cdeda72cff6bd2d/src/mirage/mirage.ml#L144) but the problem would be, only body is being checked, no headers etc. - but tried to use it for now and change it later - after trying, it still didn't look good
  - checked [`lwt`](https://github.com/ocsigen/lwt)
  - tried to focus on `total_input` - `let total_input = ref 0` - but this ‘ref’ could be problematic when there’s several threads
  - the ‘Atomic’ of it - this could mutate different thread at the same time like lock mutex, mutate my variable, release mutex ([reference](https://www.guru99.com/mutex-vs-semaphore.html))
  - We needed to update size because `Dream` uses 1 thread 
  - these were all for thread safety - mutable mutex and ultimately for I/O - for `count_IO middleware ->for ‘let count_io = middleware`
  - But the outcome was not satisfying - decided to remove the I/O implementation (for now)
- the `rusage` (metric collection) for `memory` - this code would be better separated so we did - down part is for reporting
- the next step is analytics