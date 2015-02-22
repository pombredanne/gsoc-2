### Shellcode Encoders

Currently, `pwntools` does not have internal support for encoding shellcode to avoid detection by filters or functions which stop on terminators (e.g. `\0` or `\n`).  Previously, there was a port of Metasploit's `shikata-ga-nai` encoder which was available in pwntools.

Porting this encoder back into the current `pwntools`, as well as adding additional encoders for alternate architectures, would be extremely useful for exploitation.  In particular, `pwntools` currently goes to great lengths to ensure that most shellcode that is generated is NULL- and newline-free.  Adding encoders would allow use of `pwntools`-generated for the remaining shellcode, and ease the constraints on existing shellcode.


#### Skills Required

- Python
- Assembly

#### Resources

- [Shellcoder's Handbook](http://www.amazon.com/The-Shellcoders-Handbook-Discovering-Exploiting/dp/047008023X)
- [Metasploit: Low Level](http://www.exploit-db.com/wp-content/themes/exploit/docs/18532.pdf)

#### Difficulty Level

Medium (port old encoder to current `pwntools`) to High (porting other encoders)

#### Potential Mentors

- `ebeip90`
- `Idolf`
- `br0ns`
