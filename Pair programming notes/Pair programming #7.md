- in recursion, el is for current element, rest is for rest of the element
- The not-equal-to operator ( != ) returns true if the operator don't have the same value; otherwise, it returns false
<br>

- For unique visitors, we need IP or cookie but we don’t want that. don't want to store
- for `top source`, we implemented `referer (top referer)` inside of dream_dashboard.ml
- implemented `top_os`, `top_devices`
- For log, we need to create `reporter` -> Possible problem: in Dream, the reporter seems huge for data structure and it doesn’t look so good with our code. Checked `report`, `log` on Dream’s repo -> gonna talk to Anton and check what we could do.
- should create `timestamp` for graph building:
  - Timestamp: A timestamp is a sequence of characters or encoded information identifying when a certain event occurred, usually giving date and time of day, sometimes accurate to a small fraction of a second. The default format of the timestamp contained in the string is `yyyy-mm-dd hh:mm:ss`
- For CPU, the code for metrics seems not correct in info.ml - need to fix
- did refactoring - split and made 2 libraries
- we need to start talking with the UI designer

<br>

- Tried to get `load` with Patrik ([link](https://github.com/JiaeK/dream-dashboard/compare/main...pkel:main)) - reference of unix [load](https://en.wikipedia.org/wiki/Load_(computing))

<br>

- Tried to implement `opened file descriptors` with Jon using `Unix.getpid ()`:
  1. ran `ps aux`
  2. used the PID from the result to see which files are opened with command e.g. `ls -l /proc/29242/fd`
  - How do I open a file descriptor: On Linux, the set of file descriptors open in a process can be accessed under the path `/proc/PID/fd/` , where PID is the process identifier. File descriptor `/proc/PID/fd/0` is `stdin` , `/proc/PID/fd/1` is `stdout` , and `/proc/PID/fd/2` is `stderr`
  - Having the list of files and network sockets with the TCP port would be useful for instance: it would allow us to see if we’re opening too many files, or making too many HTTP requests
  - this was just for counting opened file descriptors
