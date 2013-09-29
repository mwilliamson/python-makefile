Standard makefile for my Python projects. Assumes:

* tests are run using nose
* any test dependencies are specified in the requirements file `test-requirements.txt`
* README.md exists

## Targets

### bootstrap

Get hacking on the project. Creates a virtualenv under `_virtualenv` and
installs the project and its dependencies in the virtualenv.

### test

Runs all tests under the directory `tests`. This looks through all Python files,
but all test functions must use nose's `@istest` decorator. In other words,
the names of files and functions is irrelevant.

Before running the tests or after updating the list of dependencies,
you should run `make bootstrap`.
This is not done as part of `make test` since this can slow down the tests considerably
in the common case of everything already being up-to-date.
    
### upload

Upload the package to PyPI.
Requires pandoc to be installed so that `README` is created properly.
    
### register

Register the package with PyPI.

### README

Creates `README` by converting `README.md` from Markdown to reStructuredText using pandoc.
If pandoc is not installed, then it simply copies `README.md` to `README`.
