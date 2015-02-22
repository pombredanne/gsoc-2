### Mac OS X Support

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
