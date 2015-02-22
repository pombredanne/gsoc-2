
### Port Doctests to a Unit Testing Framework

Currently, all of the tests are run as part of a wrapper via `sphinx`.  This places a large number of restrictions on the tests, and requires manual addition to the corpus rather than automated test enumeration.  Ideally, test discovery would be automated, and handle both doctests and unit tests.  Both `nosetests` and `py.test` are excellent candidates for this, but there are expectations built into the current tests which preclude the use of these frameworks.

#### Skills Required

- Python
- Linux

#### Resources

- [Testing Your Code - Hitchhiker's Guide to Python](http://docs.python-guide.org/en/latest/writing/tests/)
- [PyTest.org](http://pytest.org/latest/)
- [An Introduction to Travis-CI](http://www.slideshare.net/Gengo/travis-ci-26008691)

#### Difficulty Level

Low

#### Potential Mentors

- `ebeip90`
- `Idolf`
- `br0ns`
