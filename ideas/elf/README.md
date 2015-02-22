### Enhancements to `pwnlib.elf` module for editing ELFs

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
