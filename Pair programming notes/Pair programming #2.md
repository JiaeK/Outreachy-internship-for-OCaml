- Implemented `uptime` in [.mli](https://github.com/JiaeK/dream-dashboard/blob/36ce89f5f2610788ca8195fb80b22cbf64eb01ce/src/info.mli#L29) & [.ml](https://github.com/JiaeK/dream-dashboard/blob/36ce89f5f2610788ca8195fb80b22cbf64eb01ce/src/info.ml#L22) files
- To return to `CPU`, we have to check [metrics_rusage](https://mirage.github.io/metrics/metrics-rusage/Metrics_rusage/index.html), metrics library for `rusage`
- `name -> process (struct) -> pid`
  - `PID` in the project's context: it stands for “Process Identifier”. When the operating system creates new processes, it assigns them an unique identifier (ID), so it can manage them
  - `PID` in general context: the algorithm which used in robotics to reduce noise from a sensor’s input by averaging the signal with its derivative (and other values calculated in the algorithm, the integral, etc.)
  - ? Could a cache reporter be useful ?
  - [reference](https://github.com/roburio/albatross/blob/3cf3d6dc56868a800967cbca2b29e743e7b2d487/stats/albatross_stat_client.ml) (linux only)
- For `metrics lwt`: reference [builder-web. robur](https://git.robur.io/robur/builder-web/src/branch/login/http_status_middleware/http_status_metrics.ml)
- `let*` : [Monads](https://cs3110.github.io/textbook/chapters/ds/monads.html) 
- the metrics code we implemented today was about `function -> loop` so we only can see and users can’t see yet => need to find some method to show to users
- CPU calculating reference:
  1. https://stackoverflow.com/questions/8501706/how-to-get-the-cpu-usage-in-c/8501750#8501750
  2. https://stackoverflow.com/questions/1420426/how-to-calculate-the-cpu-usage-of-a-process-by-pid-in-linux-from-c/1424556#1424556
