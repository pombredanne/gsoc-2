## About Binjitsu

### What is binjitsu and pwntools?

`pwntools` is an open-source, MIT-licensed framework for automating and aiding in the development of exploits for Capture The Flag computer security competitions.  `binjitsu` is a fork of this project that is developed more rapidly, which contributes changes back to the main `pwntools` project.

In particular, `pwntools` provides commonly-used functionality which are frequently re-implemented by exploit authors for each exploit, or copy-pasted around.  Additionally, it provides assistance in the exploit development process by automating some operations, or providing automated analysis and discovery about a program.

**If you're unfamiliar with Capture the Flag and Competitive Hacking, you should watch [this video!](https://www.youtube.com/watch?v=ECMExVt1lbI).**

### Why is it interesting?

Hollywood glamorizes hacking and hackers, but the truth is that computer security, vulnerability research, and exploit development are much more tedious than what's shown on the silver screen.  While we'll never reach a place where we have [crazy 3D cube exploit auto-generators][3], we can certainly strive to make each part easier, faster, and more enjoyable.

[3]: https://www.youtube.com/watch?v=cmR3wIBJZbk

### Who uses it?

`pwntools` is widely used throughout the Capture the Flag and Wargames community.  It's primarily developed by the Gallopsled CTF team, which use it exclusively.  Its has spread among the community because of its ease of use and utility.

One of the common post-competition activities for CTF is to post a write-up of the challenge binary.  Generally, this includes an analysis of the binary, its vulnerabilities, and details on the exploitation process.  Searching Google for `"from pwn import"` yields about 1300 hits, almost all of which are unique write-ups from different authors.

### What language is it written in?

`pwntools` is written exclusively in Python, and targets Python 2.7.

### How is it going to change the world?

`pwntools` is already an excellent resource for experienced competitors, but ideally would also be a teaching resource.  Many of the pitfalls that are encountered when starting out with reverse engineering and exploit development are side-stepped by using `pwntools`, because it was written with knowledge of those pitfalls.

By making computer security and exploitation more approachable, we can enhance general awareness about common security-related mistakes which lead to memory corruption and eventually code execution.
