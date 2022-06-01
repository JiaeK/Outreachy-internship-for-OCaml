
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
 
| Overview page | Analytics page | Monitoring page | Logs page |
| --------------- | --------------- | --------------- | --------------- |
| - Version of OCaml |- Number of visitors| - Memory usage |- Report logs |
| - Version of Dream | - Top countries |- CPU usage |
| - Version of the dashboard | - Top sources | - Opened file descriptors |
| - Uptime | - Top pages | - Total I/O (input and output measured in Gb) |
| - Host system information (OS, architecture, etc.) |- Devices | 
| | - Browser |
| | - Operating system |
 


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


<details>
 <summary><b> Overview of workflow as in chart (click to expand) </b></summary>
 
![d workflow](https://user-images.githubusercontent.com/78751231/171394583-9bad32cc-ab1c-4f99-a3c3-6448cae7bccd.png)
</details>


#### ▪️Table of pair programming (=pp) notes and workflow
0. 
1. pp #1
2.
3.
4.
5.
6.
7.
8.
9. 
10. 
11. 
12. 
13. 
14. 
15. 


<br>

## 🗺️ Planned Outlook 
*Disclaimer: this UI design and code all exist in the codebase but the actual outlook when the PR merged point is different like the next paragraph*
#### ▪️Overview page

<br>

## 📺 Final Presentation
Watch the final public presentation I organised & hosted with my fellow interns: [here](https://watch.ocaml.org/videos/watch/f3829e4b-e2cd-443e-8502-f406e893fe5f)

<br>

## Aknowlegdement
- This project is inspired by 
- UI design by Asaad Mahmood

