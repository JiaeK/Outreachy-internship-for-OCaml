- System load: In UNIX computing, the system load is a measure of the amount of computational work that a computer system performs
- The Transmission Control Protocol (TCP) is a transport protocol that is used on top of IP to ensure reliable transmission of packets. TCP includes mechanisms to solve many of the problems that arise from packet-based messaging, such as lost packets, out of order packets, duplicate packets, and corrupted packets
- A file descriptor is a number that uniquely identifies an open file in a computer's operating system. It describes a data resource, and how that resource may be accessed. When a program asks to open a file — or another data resource, like a network socket — the kernel: Grants access
- did a research of dashboard designs and gave feedbacks to the UI designer

<br>

- we need plugin for hooking logs and analytics to our UI design code
- we still use `proc_cpu_src`
- implemented `luv` and `os_fd`
- src is data
- in info.ml `let uptime` changed to `Luv.Resource` (to assign variable)
- in my_metrics.ml, implemented `type loadavg` + `let read_loadavg`
- Reason why we do loadavg in 1, 5, 15 mins: in Sys.info in C language return them to mimic loadavg. it’s convention coming form Sys
- Also using `luv`, implemented `memory usage` - it has 3 types which are `free`, `total`, `constraint` (skip this one for now), and they are all integers:
``` 
let read_memory () =
  let free = Unsigned.UInt64.to_int (Luv.Resource.free_memory ()) in
  let total = Unsigned.UInt64.to_int (Luv.Resource.total_memory ()) in
  { free; total }
```
- `Unsigned.UInt64.to_int` above is the function
- Erased metrics in ‘lib/dream-monitoring/info.ml’ and adjust + put inside of [`my_metrics.ml`](https://github.com/JiaeK/dream-dashboard/blob/ab28db52122503e713a0cd2b6390737f873a9b48/src/my_metrics.ml#L131)
- instead of  the data running periodically, we want to get a list of data points & So we needed to create a new reporter
- [Reporter](https://github.com/JiaeK/dream-dashboard/blob/ab28db52122503e713a0cd2b6390737f873a9b48/src/my_metrics.ml#L107) is metrics. whenever a new data point is created, store it somewhere. the list isn’t good, cue would be better. For now we just created a data point list
- implemented  the [`reporter`](https://github.com/JiaeK/dream-dashboard/blob/ab28db52122503e713a0cd2b6390737f873a9b48/src/my_metrics.ml#L156) for loadavg
- [`src_map := Src_map.add src (tags, data :: previous_data) !src_map;`](https://github.com/JiaeK/dream-dashboard/blob/ab28db52122503e713a0cd2b6390737f873a9b48/src/my_metrics.ml#L120) : map like dictionary for keys(src) which values tags, previous datapoint 
- in my_metrics.ml, we added [`init_metrics`](https://github.com/JiaeK/dream-dashboard/blob/ab28db52122503e713a0cd2b6390737f873a9b48/src/my_metrics.ml#L131), this asks the users to coop and allow
- implemeted [`get_metrics`](https://github.com/JiaeK/dream-dashboard/blob/ab28db52122503e713a0cd2b6390737f873a9b48/src/my_metrics.ml#L136), which is a function to get the list of data points. cache-reporter acts as a value
- Data -> list. we mapped this list: `list -> List.map` (For [`loadavg`](https://github.com/JiaeK/dream-dashboard/blob/ab28db52122503e713a0cd2b6390737f873a9b48/src/my_metrics.ml#L167), for [`memory`](https://github.com/JiaeK/dream-dashboard/blob/ab28db52122503e713a0cd2b6390737f873a9b48/src/my_metrics.ml#L186))
- `[@@@ocaml.warning "-32"]` is telling the compiler not to complain about the prototype/problematic code
- in the Dream templates when it starts with `<%s` means strings. `<%f` means floats
- Load average is like the sum divided by number of cores
- in `opened file descriptors`, Having the list of files and network sockets with the TCP port would be useful for instance: it would allow us to see if we’re opening too many files, or making too many HTTP requests
