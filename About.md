<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [What software are you creating?](#what-software-are-you-creating)
- [Why is it interesting?](#why-is-it-interesting)
- [Who uses it?](#who-uses-it)
- [What language is it written in?](#what-language-is-it-written-in)
- [How is it going to change the world?](#how-is-it-going-to-change-the-world)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

### What software are you creating?

Pwntools is an open-source, MIT-licensed framework for automating and aiding in the development of exploits for Capture The Flag computer security competitions.

In particular, pwntools provides commonly-used functionality which are frequently re-implemented by exploit authors for each exploit, or copy-pasted around.  Additionally, it provides assistance in the exploit development process by automating some operations, or providing automated analysis and discovery about a program.

### Why is it interesting?

Hollywood glamorizes hacking and hackers, but the truth is that computer security, vulnerability research, and exploit development are much more tedious than what's shown on the silver screen.  While we'll never reach a place where we have [crazy 3D cube exploit auto-generators][3], we can certainly strive to make each part easier, faster, and more enjoyable.

[3]: https://www.youtube.com/watch?v=cmR3wIBJZbk

### Who uses it?

Pwntools is widely used throughout the Capture the Flag and Wargames community.  It's primarily developed by the Gallopsled CTF team, which use it exclusively.  Its has spread among the community because of its ease of use and utility.

One of the common post-competition activities for CTF is to post a write-up of the challenge binary.  Generally, this includes an analysis of the binary, its vulnerabilities, and details on the exploitation process.  Searching Google for `"from pwn import"` yields about 1300 hits, almost all of which are unique write-ups from different authors.

### What language is it written in?

Pwntools is written exclusively in Python.  Its dependencies are almost all written in Python, with the exception of `libcapstone` and dependencies on system binaries (e.g. `gcc`).

### How is it going to change the world?

Pwntools is already an excellent resource for experienced competitors, but ideally would also be a teaching resource.  Many of the pitfalls that are encountered when starting out with reverse engineering and exploit development are side-stepped by using `pwntools`, because it was written with knowledge of those pitfalls.

Eventually, the goal is to integrate `pwntools` into a MOOC like those that are provided Khan Academy.  In order for this to happen, `pwntools` has to be robust, easy-to-use, and well-tested.