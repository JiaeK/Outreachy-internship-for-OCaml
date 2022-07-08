# 🐫 Documentation of my Outreachy internship working with OCaml 🐫

### 🪧 Table of Contents
- [General info](https://github.com/JiaeK/Outreachy-internship-for-OCaml/blob/main/README.md#-general-info)
- [Features](https://github.com/JiaeK/Outreachy-internship-for-OCaml/blob/main/README.md#-features)
- [Overview of workflow & pair programming](https://github.com/JiaeK/Outreachy-internship-for-OCaml/blob/main/README.md#-overview-of-workflow--pair-programming)
  - [Overview of workflow as in chart](https://github.com/JiaeK/Outreachy-internship-for-OCaml/blob/main/README.md#overview-of-workflow-as-in-chart)
  - [Table of pair programming notes and workflow](https://github.com/JiaeK/Outreachy-internship-for-OCaml/blob/main/README.md#table-of-pair-programming-notes-and-workflow)
- [Planned outlook](https://github.com/JiaeK/Outreachy-internship-for-OCaml/blob/main/README.md#%EF%B8%8F-planned-outlook)
- [Outlook (when the PR was merged)](https://github.com/JiaeK/Outreachy-internship-for-OCaml/blob/main/README.md#-outlook-when-the-pr-was-merged)
- [Developed with](https://github.com/JiaeK/Outreachy-internship-for-OCaml/blob/main/README.md#-developed-with)
- [Acknowledgement](https://github.com/JiaeK/Outreachy-internship-for-OCaml/blob/main/README.md#acknowlegdement)


<br>
<br>

## 📣 General info
- Project’s name: <ins>**Building a monitoring and analytics dashboard for OCaml.org**</ins>
- Purpose: Providing visibility on server performance and usage to OCaml.org users (metrics, statistics, analytics)

- Mentor: Thibaut Mattio (@tmattio)


### 📣 Source links

- Demo repository link: [github.com/JiaeK/dream-dashboard](https://github.com/JiaeK/dream-dashboard)

- PR: https://github.com/ocaml/ocaml.org/pull/399 (merged on the 9 of April, 2022)

- Currently upstreaming on [ocaml.org/dashboard/](https://ocaml.org/dashboard/)
 
- Source code is located in [ocaml.org/src/](https://github.com/ocaml/ocaml.org/tree/main/src/dream_dashboard) repo

- Next step suggestion is [here](https://github.com/ocaml/ocaml.org/issues/410) 


<br>
<br>

## 🌈 Features 
- [x] *Checked box means implemented feature, `___`  means implemented & actually upstreamed feature (at the time of the PR)*

| Overview page | Analytics page | Monitoring page | Logs page |
| --------------- | --------------- | --------------- | --------------- |
| <ul><li>- [x] `Version of OCaml`</li><li> - [x] `Version of Dream`</li><li> - [x] `Version of the dashboard`</li><li> - [x] `Uptime`</li><li>- [x] `Host system information (OS, architecture, etc.)`</li></ul> | <ul><li>- [x] Number of visitors</li><li> - [x] Top countries</li><li> - [x] Top sources </li><li> - [x] `Top pages`</li><li> - [x] Devices</li><li>- [x] Browsers</li><li>- [x] Operating system </li></ul> | <ul><li>- [x] `Memory usage`</li><li>- [x] `CPU usage`</li><li>- [x] Opened file descriptors</li><li>- [ ] Total I/O (input and output measured in Gb)</li></ul> |<ul><li>- [ ] Report logs </li></ul>|


<br>
<br>


## 🧭 Overview of workflow & pair programming 


### 🔹Overview of workflow as in chart 
<img src="https://user-images.githubusercontent.com/78751231/171423548-98cf1ecf-cfa1-4a0c-9d85-519a27b13929.png" alt="Workflow overview chart" title="Workflow overview chart"
     width="75%"/>


<br>

### 🔹Table of pair programming notes and workflow 

<b>Before</b> - Get familiarise with [mirage-metrics](https://github.com/mirage/metrics) (`CPU`, `memory`), Study & reference Phoenix.LiveDashboard

[Pair programming #1](https://github.com/JiaeK/Outreachy-internship-for-OCaml/blob/main/Pair%20programming%20notes/Pair%20programming%20%231.md) - 
Basic concepts of OCaml, How to reference OCaml API when writing OCaml, OCaml syntax

[Pair programming #2](https://github.com/JiaeK/Outreachy-internship-for-OCaml/blob/main/Pair%20programming%20notes/Pair%20programming%20%232.md) - `Uptime`, Returning to `CPU`, `metrics-lwt`

[Pair programming #3](https://github.com/JiaeK/Outreachy-internship-for-OCaml/blob/main/Pair%20programming%20notes/Pair%20programming%20%233.md) - Get familiarise with `Dream`, Implement a `spin-dream` project, How to reference `build_info`, `alcotest`

[Pair programming #4](https://github.com/JiaeK/Outreachy-internship-for-OCaml/blob/main/Pair%20programming%20notes/Pair%20programming%20%234.md) - Implement `platform` & `CPU` & `uptime`, Learn about `Luv` & `ocaml-node-unix` & `I/O` & `mutex`

[Pair programming #5](https://github.com/JiaeK/Outreachy-internship-for-OCaml/blob/main/Pair%20programming%20notes/Pair%20programming%20%235.md) - `user agent`, `os`, `device info`, `events`

Pair programming #6 - Revision, Refactoring

[Pair programming #7](https://github.com/JiaeK/Outreachy-internship-for-OCaml/blob/main/Pair%20programming%20notes/Pair%20programming%20%237.md) - `top browser`, `top os`, `top devices`, `CPU usage` & Started working with UI designers

[Pair programming #8](https://github.com/JiaeK/Outreachy-internship-for-OCaml/blob/main/Pair%20programming%20notes/Pair%20programming%20%238.md) - `load average`, `memory usage`, `opened file descriptors`, Started researching dashboard designs

[Pair programming #9](https://github.com/JiaeK/Outreachy-internship-for-OCaml/blob/main/Pair%20programming%20notes/Pair%20programming%20%239.md) - Attempt to implement `log`

[Pair programming #10](https://github.com/JiaeK/Outreachy-internship-for-OCaml/blob/main/Pair%20programming%20notes/Pair%20programming%20%2310.md) - `unique visitors`, Adjust `open file descriptors, Get localization for IP addresses, Hash

Pair programming #11 - Temporary remove `log`, Get ready for upstreaming - opened PR for integration to ocaml.org , adjust TODOs

[Pair programming #12](https://github.com/JiaeK/Outreachy-internship-for-OCaml/blob/main/Pair%20programming%20notes/Pair%20programming%20%2312.md) - Rebase, Add the total count of unique visitors, Fix `memory usage` & `uptime`, Remove `I/O` for now

[Pair programming #13](https://github.com/JiaeK/Outreachy-internship-for-OCaml/blob/main/Pair%20programming%20notes/Pair%20programming%20%2313.md) - Aggregate, Make it more reponsive, Remove unuse code for now

[Pair programming #14](https://github.com/JiaeK/Outreachy-internship-for-OCaml/blob/main/Pair%20programming%20notes/Pair%20programming%20%2314.md) - Rebase, Update privacy policy, Check everything before go upstream, Open an issue for the next steps



<br>
<br>


## 🗺️ Planned outlook 
*Disclaimer: this UI design and all the foundations of back-end code exist inside of the repo, but the actual outlook when the PR was merged is different as shown in the next paragraph*
#### 🔹Overview page
![dash o](https://user-images.githubusercontent.com/78751231/177977860-8dc645a7-ef75-462c-b027-1e356351d35f.png)


#### 🔹Monitoring page
![dash m](https://user-images.githubusercontent.com/78751231/177977890-bdbc26ff-8061-46e1-b162-eeae0d806e19.png)


#### 🔹Analytics page
![dash a1](https://user-images.githubusercontent.com/78751231/177977911-f482dc0b-a3d1-4520-a7a2-ec729c3f7661.png)
![dash a2](https://user-images.githubusercontent.com/78751231/177977931-3867560f-4f93-457b-a280-4cfe90bc3093.png)


<br>
<br>


## 📈 Outlook (when the PR was merged)
#### 🔹Overview page
![dashboard overview 3 25 2022](https://user-images.githubusercontent.com/78751231/171997940-e15e272c-cdc4-4db5-918e-1b369a2925e0.png)


#### 🔹Analytics page
![dashboard analytics 3 25 2022](https://user-images.githubusercontent.com/78751231/171997946-045ac617-4b29-4d71-a90b-eff09349e4bf.png)


<br>
<br>


## 🔧 Developed with 
- [OCaml](https://github.com/ocaml/ocaml) : A functional, statically-typed programming language from the ML family, offering a powerful module system extending that of Standard ML and a feature-rich, class-based object system
- [Dune](https://ocaml.org/p/dune/3.2.0) : A build system designed for OCaml/Reason projects
- [Dream](https://ocaml.org/p/dream/1.0.0~alpha4) : Easy-to-use, feature-complete Web framework without boilerplate 
- [crunch](https://ocaml.org/p/crunch/3.2.0) : Convert a filesystem into a static OCaml module
- [dune-build-info](https://ocaml.org/p/dune-build-info/3.2.0) : Embed build informations inside executable
- [luv](https://ocaml.org/p/luv/0.5.11) : A neatly-packaged OCaml/Reason binding to libuv, the cross-platform C library that does asynchronous I/O in Node.js and runs Node's
main loop
- [metrics-lwt](https://ocaml.org/p/metrics-lwt/0.4.0) : Lwt backend for the Metrics library 
- [user-agent-parser](https://ocaml.org/p/user-agent-parser/0.2.0) : OCaml implementation of the user agent parse rules of uap-core 
- [digestif](https://ocaml.org/p/digestif/1.1.2) : Hash algorithms in C and OCaml (SHA*, RIPEMD160, BLAKE2* and MD5) 
- [alcotest](https://ocaml.org/p/alcotest/1.5.0) : A lightweight and colourful test framework that exposes a simple interface to perform unit tests
- [odoc](https://ocaml.org/p/odoc/2.1.0) : OCaml documentation generator 
- [ppx_deriving_yojson](https://ocaml.org/p/ppx_deriving_yojson/3.6.1) : A plugin that generates JSON serializers and deserializes that use the Yojson library
from an OCaml type definition
- [yojson](https://ocaml.org/p/yojson/1.7.0) : JSON library for OCaml
- [timedesc](https://ocaml.org/p/timedesc/0.6.0) : OCaml date time handling and reasoning suite
- [Tailwind CSS](https://tailwindcss.com/) : A utility-first CSS framework for rapidly building custom user interfaces
- [Alpine.js](https://alpinejs.dev/): A rugged, minimal framework for composing JavaScript behavior in your markup


<br>
<br>

### Acknowlegdement
- This project is inspired by [Phoenix.LiveDashboard](https://github.com/phoenixframework/phoenix_live_dashboard) and [plausible.io](https://plausible.io/)
- UI design by Asaad Mahmood 
- 📺 Watch the final public presentation I organised & hosted with my amazing fellow interns: [here](https://watch.ocaml.org/videos/watch/f3829e4b-e2cd-443e-8502-f406e893fe5f)
- 📰 Read more stories of my Outreachy internship experience on [my blog](https://jiaek.wordpress.com)

