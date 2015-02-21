<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Python-Only Enhancements](#python-only-enhancements)
  - [Port Doctests to a Unit Testing Framework](#port-doctests-to-a-unit-testing-framework)
  - [Extend Integration Testing Framework and Examples](#extend-integration-testing-framework-and-examples)
  - [Overhaul / re-write of the `pwnlib.term` module](#overhaul--re-write-of-the-pwnlibterm-module)
- [Exploitation Improvements](#exploitation-improvements)
  - [Multi-arch support for `pwnlib.rop`](#multi-arch-support-for-pwnlibrop)
  - [Porting Shellcode to Pwntools](#porting-shellcode-to-pwntools)
  - [Shellcode Encoders](#shellcode-encoders)
  - [SIGRET Exploitation Assitance](#sigret-exploitation-assitance)
  - [Format String Payload Generation](#format-string-payload-generation)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

This is a non-comprehensive list of general outstanding issues and "nice-to-haves" which affect both binjitsu and vanilla pwntools.

## Python-Only Enhancements

These ideas only require knowledge of Python, and do not expect experience regarding binary exploitation or Capture the Flag.

### Port Doctests to a Unit Testing Framework

Currently, all of the tests are run as part of a wrapper via `sphinx`.  This places a large number of restrictions on the tests, and requires manual addition to the corpus rather than automated test enumeration.  Ideally, test discovery would be automated, and handle both doctests and unit tests.  Both `nosetests` and `py.test` are excellent candidates for this, but there are expectations built into the current tests which preclude the use of these frameworks.

### Extend Integration Testing Framework and Examples

There is also a [regression testing][2] framework that's designed to permit automatic testing of various parts of pwntools as a whole, rather than in bite-sized prepared chunks.  This regression testing code works, but it is not complete and does not give good coverage for all of the code.

The current [examples repository][1] is a bit outdated and doesn't work with the current incarnation of pwntools or binjitsu.  Unfortunately, new users have very little options to turn to when looking for a good starting point for "How do I pwntools".

[1]: https://github.com/Gallopsled/pwntools-write-ups
[2]: https://github.com/Gallopsled/pwntools-regression

### Overhaul / re-write of the `pwnlib.term` module

This module is currently the least-well-understood module and in its current form isn't documented or tested.

Re-implementing, or re-factoring the current implementation, should allow this module to be tested in an automated manner.

### Enhancements to `pwnlib.elf` module for editing ELFs

Currently, the `pwnlib.elf` module has primitives to allow modifying arbitrary sections of the on-disk image of a loaded ELF file.  However, the limitations of the `pyelftools` library used to perform these operations prevents adding entire sections to the ELF binary, or adding relocations to it.

Extending the existing functionality to provide the ability to modify, re-order, or otherwise re-write ELF files without affecting their native functionality (a la `the-backdoor-factory`) would be a great benefit to attack-defend CTFs.

## Exploitation Improvements

These improvements require both knowledge of Python, and a good understanding of reverse engineering and exploitation primitives.

### Multi-arch support for `pwnlib.rop`

Currently, the ROP generation in the *released* version of `pwntools` does not support any architectures for automatic ROP gadget extraction, or chain building, except for on i386.

Given the increasing prevalence of x86_64, ARM, and Windows binaries, the current `pwnlib.rop` module needs to be overhauled.  In  particular, it needs support for specifying which ABI is being used, in addition to which architecture.  This is important for distinguishing x86_64 Linux vs. Windows, which use different registers to pass their arguments, as well as different stack alignments and reserved per-frame stack space.

Additionally, specification of ABIs should allow direct invokation of syscalls after properly preparing the register arguments.  While this is no different from the standard user-mode ABI on some architectures (e.g. x86_64 Linux), it differs greatly on others (i386 Linux).

### Porting Shellcode to Pwntools

Pwntools currently has a good deal of shellcode available in `pwnlib.shellcraft` for i386, amd64, and ARM.  However, there are lots of things that are missing (e.g. file-read, file-write, file descriptor proxying) which would be excellent additions to the corpus.

Porting shellcode to pwntools would require ingesting shellcode from Shell-Storm.org or ExploitDB.com, and re-writing them as Mako templates in pwntools.  Ideally, all shellcode will use (or be refactored to use) templates for common operations.

### Shellcode Encoders

Currently, `pwntools` does not have internal support for encoding shellcode to avoid detection by filters or functions which stop on terminators (e.g. `\0` or `\n`).  Previously, there was a port of Metasploit's `shikata-ga-nai` encoder which was available in pwntools.

Porting this encoder back into the current `pwntools`, as well as adding additional encoders for alternate architectures, would be extremely useful for exploitation.  In particular, `pwntools` currently goes to great lengths to ensure that most shellcode that is generated is NULL- and newline-free.  Adding encoders would allow use of `pwntools`-generated for the remaining shellcode, and ease the constraints on existing shellcode.

### SIGRET Exploitation Assitance

Currently, `pwntools` is completely unaware of SIGRET-style ROP (SROP).  Helpers for generating valid register frames for use with SROP would be very useful.

### Format String Payload Generation

Currently, `pwntools` is unable to offer any assistance in generation of format string payloads.  The open-source project `libformatstr` would serve as an excellent starting point for adding this functionality to pwntools.

Additional functionality could be added in order to enhance the robustness and automation.  For example, the `DynELF` object in `pwntools` allows automatically leaking memory to resolve symbols in remote address spaces.  A similar mechanism could be used to automate discovery of control bounds (e.g. format string input size, argument index, prefixed characters, etc.).