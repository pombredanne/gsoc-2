![](gsoc.png)

# Pwntools & Binjitsu: Google Summer of Code

Welcome to the [Google Summer of Code](https://developers.google.com/open-source/soc/?csw=1) landing page for the Pwntools and Binjitsu projects!

You can find more information about the project, its mentors, project ideas, and how to get started below!

- [About Pwntools](#about-pwntools-and-binjitsu)
- [Mentors and Contact Information](#mentors)
- [Project Ideas](#project-ideas)
- [Getting Started](#getting-started)

## About Pwntools and Binjitsu

### What are binjitsu and pwntools?

[`pwntools`](https://pwntools.com) is an open-source, MIT-licensed framework for automating and aiding in the development of exploits for Capture The Flag computer security competitions.  [`binjitsu`](https://binjit.su) is a fork of this project that is developed more rapidly, which contributes changes back to the main `pwntools` project.

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

## Mentors

This is the current list of mentors for any Google Summer of Code projects.

### [Zach Riggle (ebeip90)](https://github.com/ZachRiggle)

Maintainer and developer of the `binjitsu` fork, contributor to `pwntools`.

- `ebeip90` on [Freenode](https://webchat.freenode.net/)
- `ebeip90` on [Twitter](https://twitter.com/ebeip90)
- `zachriggle` on [Github](https://github.com/zachriggle)

### [Mathias Svensson (Idolf)](https://github.com/Idolf)

Maintainer and developer of `pwntools`.

### [Morten Brøns-Pedersen (br0ns)](https://github.com/br0ns)

Maintainer and developer of `pwntools`.

## Getting in Touch

The best way to get ahold of us is on IRC! Feel free to join and introduce yourself, or ask any questions you may have!


- IRC channel: `#pwning` on Freenode
- Nicks: `ebeip90`, `IdolfHatler`, `br0ns`


## Getting Started

Pwntools is designed to get you up and running as fast as possible!

### Getting the Software

Getting started with Binjitsu is easy!  If you're using Ubuntu, only a few commands away.

```
$ apt-get install python2.7 python2.7-dev python-pip
$ git clone https://github.com/binjitsu/binjitsu
$ cd binjitsu
$ pip install -e .
```

### First Steps and Examples

The online documentation has a [Getting Started](http://binjitsu.readthedocs.org/en/latest/intro.html) section for demonstrating some of the basic features.  More advanced use cases be found in the [write-ups](https://github.com/Gallopsled/pwntools-write-ups) repository, or [just by searching Google for `from pwn import *`](https://www.google.com/webhp#q=%22from+pwn+import%22)!

### Contributing and Source Control

Both `pwntools` and `binjitsu` use [Github](https://github.com) for source control and [Travis CI](https://travis-ci.com) for automatic testing.

Instructions on getting up and running with a local copy for development are available in [CONTRIBUTING.md](https://github.com/binjitsu/binjitsu/blob/master/CONTRIBUTING.md) for each project.

## Project Ideas

This is the current list of ideas, sorted in general order of "easiest" to "hardest".

##### Python-Only Enhancements

These ideas only require knowledge of Python, and do not expect experience regarding binary exploitation or Capture the Flag.

- [Unit Testing](#unit)
- [Integration Testing](#integration)
- [ELF Modification](#elf)
- [OS X Compatibility](#mac)
- [Windows PE Support](#pe)
- [Terminal Revamp](#term)

##### Exploitation Improvements

These improvements require both knowledge of Python, and a good understanding of reverse engineering and exploitation primitives.

- [Moar Exploits!](#exploits)
- [Moar Shellcode!](#shellcode)
- [SIGRET Assistance](#sigret)
- [Format Strings](#format)
- [Shellcode Encoders](#encoders)
- [Multi-Architecture ROP](#ROP)

### <a name="unit"></a>Port Doctests to a Unit Testing Framework

Pwntools is surprisingly well tested for an exploit development framework -- it currently has over 900 tests. All of the tests are currently implemented as doctests, and run automatically by `sphinx`.

However, `sphinx` is not very flexible, and running tests is not its primary purpose (`sphinx` is for generating documentation -- but will also run basic doctests).  This places a large number of restrictions on the tests, and requires manual addition to the corpus rather than automated test enumeration.

Ideally, test discovery would be automated, and handle both doctests and unit tests.  Both `nosetests` and `py.test` are excellent candidates for this, but there are expectations built into the current tests which preclude the use of these frameworks.

#### Skills Required

- Python
- Linux

#### Resources

- [Testing Your Code - Hitchhiker's Guide to Python](http://docs.python-guide.org/en/latest/writing/tests/)
- [PyTest.org](http://pytest.org/latest/)
- [Continuous Integration in Python: Travis-CI](http://ilovesymposia.com/2014/10/15/continuous-integration-in-python-4-set-up-travis-ci/)

#### Difficulty Level

Low

#### Potential Mentors

- `ebeip90`
- `Idolf`
- `br0ns`

[![up](http://fa2png.io/static/images/level-up_808080_16.png)](#project-ideas)

### <a name="integration"></a>Extend Integration Testing Framework and Examples

There is also a [regression testing][2] framework that's designed to permit automatic testing of various parts of pwntools as a whole, rather than in bite-sized prepared chunks.  This regression testing code works, but it is not complete and does not give good coverage for all of the code.

The current [examples repository][1] is a bit outdated and doesn't work with the current incarnation of pwntools or binjitsu.  Unfortunately, new users have very little options to turn to when looking for a good starting point for "How do I pwntools".

[1]: https://github.com/Gallopsled/pwntools-write-ups
[2]: https://github.com/Gallopsled/pwntools-regression

#### Skills Required

- C
- Python
- Linux

#### Resources

- [Integration Testing (Wikipedia)](http://en.wikipedia.org/wiki/Integration_testing)

#### Difficulty Level

Low to medium

#### Potential Mentors

- `ebeip90`
- `Idolf`
- `br0ns`

[![up](http://fa2png.io/static/images/level-up_808080_16.png)](#project-ideas)

### <a name="elf"></a>Enhancements to `pwnlib.elf` module for editing ELFs

Currently, the `pwnlib.elf` module has primitives to allow modifying arbitrary sections of the on-disk image of a loaded ELF file.  However, the limitations of the `pyelftools` library used to perform these operations prevents adding entire sections to the ELF binary, or adding relocations to it.

Extending the existing functionality to provide the ability to modify, re-order, or otherwise re-write ELF files without affecting their native functionality (a la `the-backdoor-factory`) would be a great benefit to attack-defend CTFs.

#### Skills Required

- Python
- Linux

#### Resources

- [Executable and Linkable Format (Wikipedia)](http://en.wikipedia.org/wiki/Executable_and_Linkable_Format)
- [the-backdoor-factory](https://github.com/secretsquirrel/the-backdoor-factory)

#### Difficulty Level

Medium

#### Potential Mentors

- `ebeip90`
- `Idolf`
- `br0ns`

[![up](http://fa2png.io/static/images/level-up_808080_16.png)](#project-ideas)

### <a name="mac"></a>Mac OS X Support

Currently, `pwntools` and `binjitsu` work best on Linux distributions like Ubuntu.  
However, lots of developers prefer to use alternate operating systems like Mac OS X,
and some future challenges may even be written for it.

This project would require making changes to `binjitsu` to make as many unit tests
as possible pass on Mac OS X, integrating these with Travis CI, and perhaps even
writing some integration tests to ensure end-to-end functionality.

A stretch goal would be to extend the current generation and parsing of ELF files
to include the Mach-O format used by OS X.

#### Skills Required

- Python
- Linux
- OS X

#### Resources

- [Porting UNIX/Linux Applications to OS X](https://developer.apple.com/library/mac/documentation/Porting/Conceptual/PortingUnix/intro/intro.htm)
- [Mach-O (Wikipedia)](http://en.wikipedia.org/wiki/Mach-O)

#### Difficulty Level

Medium

#### Potential Mentors

- `ebeip90`

[![up](http://fa2png.io/static/images/level-up_808080_16.png)](#project-ideas)

### <a name="pe"></a>Windows PE File Support

Currently, `pwntools` and `binjitsu` have a lot of helper utilities for loading,
parsing, and extracting information from Linux ELF files.  However, the same 
level of support is not present for Windows PE files.

The goal of this project would be to create a compatibility layer between the
current ELF functionality based on `pyelftools`, and the Python PE library, `pefile`.

#### Skills Required

- Python
- Linux
- Windows

#### Resources

- [PEFile](https://code.google.com/p/pefile/)
- [PyElfTools](https://github.com/eliben/pyelftools)
- [PE 101](http://corkami.googlecode.com/files/PE101-v1.pdf)
- [ELF 101](https://corkami.googlecode.com/files/elf101.pdf)

#### Difficulty Level

Medium

#### Potential Mentors

- `ebeip90`
- `Idolf`
- `br0ns`

[![up](http://fa2png.io/static/images/level-up_808080_16.png)](#project-ideas)

### <a name="term"></a>Overhaul / re-write of the `pwnlib.term` module

This module is currently the least-well-understood module and in its current form isn't documented or tested.

Re-implementing, or re-factoring the current implementation, should allow this module to be tested in an automated manner.

#### Skills Required

- Python
- Linux

#### Resources

- [Terminal Emulation (Wikipedia)](http://en.wikipedia.org/wiki/Terminal_emulator)
- [Curses (Python Library)](https://docs.python.org/2/library/curses.html)

#### Difficulty Level

Low to medium

#### Potential Mentors

- `ebeip90`
- `Idolf`
- `br0ns`

[![up](http://fa2png.io/static/images/level-up_808080_16.png)](#project-ideas)

## <a name="exploits"></a>More Exploit Examples!

There are easily hundreds of different exploits available [just from searching Google](https://www.google.com/webhp#q=%22from+pwn+import%22).
Unfortunately, these aren't all in one central location, and aren't being used to verify
that we're aware of any feature-breaking changes that we make.

This project would involve finding well-written exploits using `pwntools` 
(or re-writing other exploits to use it) and collecting them into the 
`pwntools-write-ups` repository.

After a good number are gathered and in working condition, a wrapper should
be developed to ensure that the exploits all work with a single command, so
that this can be integrated into the Continuous Integration tests.

#### Skills Required

- Python
- Linux
- Willing to learn!

#### Resources

- [pwntools-write-ups](https://github.com/Gallopsled/pwntools-write-ups)
- [Google: "from pwn import *"](https://www.google.com/webhp#q=%22from+pwn+import%22)

#### Difficulty Level

Varies wildly, from low to very high

#### Potential Mentors

- `ebeip90`
- `Idolf`
- `br0ns`

[![up](http://fa2png.io/static/images/level-up_808080_16.png)](#project-ideas)

### <a name="shellcode"></a>Porting Shellcode to Pwntools

Pwntools currently has a good deal of shellcode available in `pwnlib.shellcraft` for i386, amd64, and ARM.  However, there are lots of things that are missing (e.g. file-read, file-write, file descriptor proxying) which would be excellent additions to the corpus.

Porting shellcode to pwntools would require ingesting shellcode from Shell-Storm.org or ExploitDB.com, and re-writing them as Mako templates in pwntools.  Ideally, all shellcode will use (or be refactored to use) templates for common operations.

#### Skills Required

- Python
- Assembly
- Linux

#### Resources

- [Shell-Storm Shellcode Database](http://shell-storm.org/shellcode/)
- [ExploitDB Shellcode Database](http://www.exploit-db.com/shellcode/)

#### Difficulty Level

Low to Moderate

#### Potential Mentors

- `ebeip90`
- `Idolf`
- `br0ns`

[![up](http://fa2png.io/static/images/level-up_808080_16.png)](#project-ideas)

### <a name="sigret"></a>SIGRET Exploitation Assitance

Currently, `pwntools` is completely unaware of SIGRET-style ROP (SROP).  Helpers for generating valid register frames for use with SROP would be very useful.

#### Skills Required

- Python
- Linux
- Familiar with ROP

#### Resources

- [Framing Signals - A Return to Portable Shellcode](https://www.cs.vu.nl/~herbertb/papers/srop_sp14.pdf)
- [Playing around with SROP](http://x86overflow.blogspot.com/2014/04/playing-around-with-srop.html)
- [An overview on Sigreturn Oriented Programming](http://thisissecurity.net/2015/01/03/playing-with-signals-an-overview-on-sigreturn-oriented-programming/)

#### Difficulty Level

Medium

#### Potential Mentors

- `ebeip90`
- `Idolf`
- `br0ns`

[![up](http://fa2png.io/static/images/level-up_808080_16.png)](#project-ideas)

### <a name="format"></a>Format String Payload Generation

Currently, `pwntools` is unable to offer any assistance in generation of format string payloads.  The open-source project `libformatstr` would serve as an excellent starting point for adding this functionality to pwntools.

Additional functionality could be added in order to enhance the robustness and automation.  For example, the `DynELF` object in `pwntools` allows automatically leaking memory to resolve symbols in remote address spaces.  A similar mechanism could be used to automate discovery of control bounds (e.g. format string input size, argument index, prefixed characters, etc.).

#### Skills Required

- Python
- Linux

#### Resources

- [libformatstr](https://github.com/hellman/libformatstr)
- [Format String Vulnerabilities](http://jbremer.org/format-string-vulnerabilities/)

#### Difficulty Level

Low to medium

#### Potential Mentors

- `ebeip90`
- `Idolf`
- `br0ns`

[![up](http://fa2png.io/static/images/level-up_808080_16.png)](#project-ideas)

### <a name="encoders"></a>Shellcode Encoders

Currently, `pwntools` does not have internal support for encoding shellcode to avoid detection by filters or functions which stop on terminators (e.g. `\0` or `\n`).  Previously, there was a port of Metasploit's `shikata-ga-nai` encoder which was available in pwntools.

Porting this encoder back into the current `pwntools`, as well as adding additional encoders for alternate architectures, would be extremely useful for exploitation.  In particular, `pwntools` currently goes to great lengths to ensure that most shellcode that is generated is NULL- and newline-free.  Adding encoders would allow use of `pwntools`-generated for the remaining shellcode, and ease the constraints on existing shellcode.


#### Skills Required

- Python
- Assembly

#### Resources

- [Shellcoder's Handbook](http://www.amazon.com/The-Shellcoders-Handbook-Discovering-Exploiting/dp/047008023X)
- [Metasploit: Low Level](http://www.exploit-db.com/wp-content/themes/exploit/docs/18532.pdf)
- [Cascading Polymorphic XOR Encoder in Python](http://www.iodigitalsec.com/python-cascading-xor-polymorphic-shellcode-generator/)
- [ALPAH3 Shellcode Encoder](https://code.google.com/p/alpha3/)
- [SLAE - Custom RBIX Shellcode Encoder](https://www.rcesecurity.com/2015/01/slae-custom-rbix-shellcode-encoder-decoder/)

#### Difficulty Level

Medium (port old encoder to current `pwntools`) to High (porting other encoders)

#### Potential Mentors

- `ebeip90`
- `Idolf`
- `br0ns`

[![up](http://fa2png.io/static/images/level-up_808080_16.png)](#project-ideas)

### <a name="ROP"></a>Multi-arch support for `pwnlib.rop`

#### Description

Currently, the ROP generation in the *released* version of `pwntools` does not support any architectures for automatic ROP gadget extraction, or chain building, except for on i386.

Given the increasing prevalence of x86_64, ARM, and Windows binaries, the current `pwnlib.rop` module needs to be overhauled.  In  particular, it needs support for specifying which ABI is being used, in addition to which architecture.  This is important for distinguishing x86_64 Linux vs. Windows, which use different registers to pass their arguments, as well as different stack alignments and reserved per-frame stack space.

Additionally, specification of ABIs should allow direct invokation of syscalls after properly preparing the register arguments.  While this is no different from the standard user-mode ABI on some architectures (e.g. x86_64 Linux), it differs greatly on others (i386 Linux).

#### Skills Required

- Python
- Linux
- Assembly
- Familiar with buffer overflows 

#### Resources

- [Return Oriented Programming (PSU.edu)](http://www.cse.psu.edu/~tjaeger/cse443-s12/slides/cse443-lecture-25-rop.pdf)

#### Difficulty Level

High, but varies depending on familiarity with the underlying technique of Return

#### Potential Mentors

- `ebeip90`
- `Idolf`
- `br0ns`

[![up](http://fa2png.io/static/images/level-up_808080_16.png)](#project-ideas)
