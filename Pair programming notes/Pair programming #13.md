- [aggregated](https://github.com/ocaml/ocaml.org/pull/399/commits/563cb688a5eee9a120cdbe3219a89bf076f37828#diff-6c299e37f37bbe1cf7d3819e0bc595078a5a9736b01a54785d259e7f1de6360e)
1. removed the UI parts of `referer`, `source`, `location`, `devices` for now
: this is because, e.g. for `location` - it’s rather more complicated than we expected - we have to map all the addresses which connect to google
2. removed unuse code from analytic template and made the comments
3. checked `ip_info` option in `event.ml` 
- we need to salt the hash = hash it better
- updated TODOs
- made it more responsive for desktop and mobile etc.
- nav bar in layout_template.eml
- You can write booleans inside of HTML tag too 
: e.g.)  `class="<%s if nav = Overview then "bg-gray-900 text-white" else "text-gray-300 hover:bg-gray-700 hover:text-white" %>`
- interval was 10.0 but we changed to 60 sec => let init_metrics ?(interval = 60.0) 
