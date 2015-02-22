## About Binjitsu

### What is binjitsu and pwntools?

`pwntools` is an open-source, MIT-licensed framework for automating and aiding in the development of exploits for Capture The Flag computer security competitions.  `binjitsu` is a fork of this project that is developed more rapidly, which contributes changes back to the main `pwntools` project.

In particular, `pwntools` provides commonly-used functionality which are frequently re-implemented by exploit authors for each exploit, or copy-pasted around.  Additionally, it provides assistance in the exploit development process by automating some operations, or providing automated analysis and discovery about a program.

**If you're unfamiliar with Capture the Flag, Trail of Bits has an excellent introduction [here](https://trailofbits.github.io/ctf/intro/README.html).**

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

Eventually, the goal is to integrate `pwntools` into a MOOC like those that are provided Khan Academy.  In order for this to happen, `pwntools` has to be robust, easy-to-use, and well-tested.


###

Links to setup instructions go here. Some suggested things to answer:

Where is the link to a setup gcuide for new developers?
Are there any unusual libraries/applications that need to be installed first?
What type of source control do you use? (include links to help and setup guides!)
What's the process for submitting your first bug fix?
Where should students look to find easy bugs to try out?
Writing your application

Links to advice about applications and the application template goes here.

Project Ideas

1. Project name

Project description: Make sure you have a high-level description that any student can understand, as well as deeper details
Skills: programming languages? specific domain knowledge?
Difficulty level: Easy/Intermediate/Hard classification (students ask for this info frequently to help them narrow down their choices)
Related Readings/Links: was there a mailing list discussion about this topic? standards you want the students to read first? bugs/feature requests?
Potential mentors: A list of mentors likely to be involved with this project, so students know who to look for on IRC/mailing lists if they have questions. (If you've had trouble with students overwhelming specific mentors, feel free to re-iterate here if students should contact the mailing list to reach all mentors.)
2. Project name

As above. etc. Unless there's a compelling reason to sort in some other order, ideas should be ordered approximately from easiest to hardest.
