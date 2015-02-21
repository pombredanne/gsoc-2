### Shellcode Encoders

Currently, `pwntools` does not have internal support for encoding shellcode to avoid detection by filters or functions which stop on terminators (e.g. `\0` or `\n`).  Previously, there was a port of Metasploit's `shikata-ga-nai` encoder which was available in pwntools.

Porting this encoder back into the current `pwntools`, as well as adding additional encoders for alternate architectures, would be extremely useful for exploitation.  In particular, `pwntools` currently goes to great lengths to ensure that most shellcode that is generated is NULL- and newline-free.  Adding encoders would allow use of `pwntools`-generated for the remaining shellcode, and ease the constraints on existing shellcode.