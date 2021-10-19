Standard makefile for my Python projects. Assumes:

* tests are run using nose
* any test dependencies are specified in the requirements file `test-requirements.txt`

## Targets

### bootstrap

Get hacking on the project. Creates a virtualenv under `_virtualenv` and
installs the project and its dependencies in the virtualenv.

### test

Runs all tests under the directory `tests` using the command `nosetests tests`.

Before running the tests or after updating the list of dependencies,
you should run `make bootstrap`.
This is not done as part of `make test` since this can slow down the tests considerably
in the common case of everything already being up-to-date.

### upload

Upload the package to PyPI.

### register

Register the package with PyPI.

## References

* [Why you shouldn't invoke setup.py directly, Paul Ganssle](https://blog.ganssle.io/articles/2021/10/setup-py-deprecated.html)
