### Format String Payload Generation

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
