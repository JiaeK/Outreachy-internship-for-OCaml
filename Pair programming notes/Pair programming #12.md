- added the total count of unique visitors  
- did some dynamics - [1](https://github.com/ocaml/ocaml.org/pull/399/commits/4e5afbe4464b834de0cecd00bf09a0016e3b5dab), [2](https://github.com/ocaml/ocaml.org/pull/399/commits/21e6bc047017b68a8e7eba12f20cd12806ec9f1d)
- we rebased:
  - Rebasing: the process of moving or combining a sequence of commits to a new base commit. Rebasing is most useful and easily visualized in the context of a feature branching workflow
 1) the `memory usage` seems wrong - need to fix
    - we shouldn’t divide with CPU counts but [this](https://github.com/ocaml/ocaml.org/blob/21e6bc047017b68a8e7eba12f20cd12806ec9f1d/src/dream_dashboard/dream_dashboard.ml#L21)
 2) deleted `I/O` for now
 3) need to fix some hard-coded ones which UI developer put
 4) the `open file descriptor` isn’t ready enough so we deleted that too for now and when we have details later, then put it back
 5) `uptime` seems doesn’t right - need to fix
    - for uptime, we used `Unix.gettimeofday` but it seems not right -> switched to use [`Timere`](https://github.com/daypack-dev/timere) - installed `timedesc`(date time handling library), and tested at the Utop while using [this function](https://github.com/daypack-dev/timere#using-timedesc-in-utop):
      ```
      #require "timedesc-tzdb.full";;
      #require "timedesc-tzlocal.unix";;
      #require "timedesc";;
      ```
 6) needed timestamps for this all - put timestamps in `my_metrics.ml` - e.g. put `timestamp` in type loadavg, type memory, next to avg 15; etc.  + put `<%s human_date_of_timestamp x.timestamp %>`
 7) instead of giving all the list like metrics, would render after 1 sec, and then 10 secs, since 1 day is 43200 secs
 8) put `timedesc` and `timestamp` inside of overview_template.eml
 9) did top pages’ hard-coded part
 10) in `event.ml`, implemented `type referer` to get favicon - we wanna use `hyper.run` and `hyper.request`




