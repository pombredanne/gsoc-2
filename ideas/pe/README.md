### Windows PE File Support

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
