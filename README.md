# 🐫 Documentation for my Outreachy internship for Ocaml 🐫

### 📣 General info
- Project’s name: Building a monitoring and analytics dashboard for ocaml.org
- Purpose: Provided the visibility on the server performance of metrics, statistics, and analytics to its site users

- Mentor: Thibaut Mattio (@tmattio)


### 📣 Source links

- Demo repository link: [github.com/JiaeK/dream-dashboard](https://github.com/JiaeK/dream-dashboard)

- PR: https://github.com/ocaml/ocaml.org/pull/399 (merged on the 9 of April, 2022)

- Currently upstreaming on [ocaml.org/dashboard/](https://ocaml.org/dashboard/)
 
- Codebase is inside of [ocaml.org/src/](https://github.com/ocaml/ocaml.org/tree/main/src/dream_dashboard) repo
- Next step suggestions is [here](https://github.com/ocaml/ocaml.org/issues/410) 

<br>

## 🌈 Features 
- [x] *Checked box means implemented feature, `___`  means implemented & actually upstreamed feature (at the time of the PR)*

| Overview page | Analytics page | Monitoring page | Logs page |
| --------------- | --------------- | --------------- | --------------- |
| <ul><li>- [x] `Version of OCaml`</li><li> - [x] `Version of Dream`</li><li> - [x] `Version of the dashboard`</li><li> - [x] `Uptime`</li><li>- [x] `Host system information (OS, architecture, etc.)`</li></ul> | <ul><li>- [x] Number of visitors</li><li> - [ ] Top countries</li><li> - [ ] Top sources </li><li> - [x] `Top pages`</li><li> - [x] Devices</li><li>- [x] Browsers</li><li>- [x] Operating system </li></ul> | <ul><li>- [x] `Memory usage`</li><li>- [x] `CPU usage`</li><li>- [x] Opened file descriptors</li><li>- [ ] Total I/O (input and output measured in Gb)</li></ul> |<ul><li>- [ ] Report logs </li></ul>|



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


## 🧭 Overview of workflow & pair programming 


#### 🔹Overview of workflow as in chart 
<img src="https://user-images.githubusercontent.com/78751231/171423548-98cf1ecf-cfa1-4a0c-9d85-519a27b13929.png" alt="Workflow overview chart" title="Workflow overview chart" width="70%"/>



#### 🔹Table of pair programming notes and workflow


<b>Before</b> - Get familiarise with [mirage-metrics](https://github.com/mirage/metrics) (CPU, memory), study & reference Phoenix.LiveDashboard

[Pair programming #1](https://github.com/JiaeK/Outreachy-internship-for-OCaml/blob/main/Pair%20programming%20notes/Pair%20programming%20%231%2C%202.md) - 
Basic concepts of OCaml, How to reference OCaml API when writing OCaml, OCaml syntax

[Pair programming #2] - Uptime, CPU, metrics-lwt

[Pair programming #3]

[Pair programming #4]

[Pair programming #5]

[Pair programming #6]

[Pair programming #7]

[Pair programming #8]

[Pair programming #9]

[Pair programming #10]

[Pair programming #11]

[Pair programming #12]

[Pair programming #13]

[Pair programming #14] - Aggregate, Make it more reponsive, Remove unuse code for now

[Pair programming #15] - Rebase, Check everything before go upstream, Open an issue for the next steps

<br>
<br>

## 🗺️ Planned Outlook 
*Disclaimer: this UI design and all the foundations of back-end code exist in the codebase but the actual outlook when the PR merged is different like the next paragraph*
#### 🔹Overview page
![dash o](https://user-images.githubusercontent.com/78751231/171993753-020a3e6d-7a9c-4e53-be33-cc903c36918e.png)

#### 🔹Monitoring page
![dash m](https://user-images.githubusercontent.com/78751231/171993800-f9bedcd6-f0ed-42dd-b92f-a33ef665a3c1.png)

#### 🔹Analytics page
![dash a1](https://user-images.githubusercontent.com/78751231/171993825-e9227600-949c-49ad-81ff-53aaf4a26ddd.png)
![dash a2](https://user-images.githubusercontent.com/78751231/171993832-17e1a2d2-1756-4c5f-81d2-e317105c32c4.png)

<br>
<br>

## 📈 Outlook (when the PR merged)
#### 🔹Overview page
![dashboard overview 3 25 2022](https://user-images.githubusercontent.com/78751231/171997940-e15e272c-cdc4-4db5-918e-1b369a2925e0.png)


#### 🔹Analytics page
![dashboard analytics 3 25 2022](https://user-images.githubusercontent.com/78751231/171997946-045ac617-4b29-4d71-a90b-eff09349e4bf.png)


<br>

## 📺 Final Presentation
Watch the final public presentation I organised & hosted with my fellow amazing interns: [here](https://watch.ocaml.org/videos/watch/f3829e4b-e2cd-443e-8502-f406e893fe5f)

<br>
<br>

### Aknowlegdement
- This project is inspired by [Phoenix.LiveDashboard](https://github.com/phoenixframework/phoenix_live_dashboard) and [plausible.io](https://plausible.io/)
- UI design by Asaad Mahmood, Mirza Babar Baig 

