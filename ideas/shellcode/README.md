### Porting Shellcode to Pwntools

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
