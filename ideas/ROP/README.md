### Multi-arch support for `pwnlib.rop`

Currently, the ROP generation in the *released* version of `pwntools` does not support any architectures for automatic ROP gadget extraction, or chain building, except for on i386.

Given the increasing prevalence of x86_64, ARM, and Windows binaries, the current `pwnlib.rop` module needs to be overhauled.  In  particular, it needs support for specifying which ABI is being used, in addition to which architecture.  This is important for distinguishing x86_64 Linux vs. Windows, which use different registers to pass their arguments, as well as different stack alignments and reserved per-frame stack space.

Additionally, specification of ABIs should allow direct invokation of syscalls after properly preparing the register arguments.  While this is no different from the standard user-mode ABI on some architectures (e.g. x86_64 Linux), it differs greatly on others (i386 Linux).
