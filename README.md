# common-build-dependencies

`common-build-dependencies` is probably the module, which you need to
`build-require` in order to build your module.

This git repository represents two modules:

 1. [`common-build-dependencies`](http://pkgs.fedoraproject.org/cgit/modules/common-build-dependencies.git/)
 2. [`common-build-dependencies-bootstrap`](http://pkgs.fedoraproject.org/cgit/modules/common-build-dependencies-bootstrap.git/)

At early stages, plenty of modules will be present only in
`common-build-dependencies-bootstrap`. You should check dist-git what's the
current content of the modules.


## Workflow

If you need to add a package to this module, please open a pull request and add
a new entry to section **Requests**.

Example:

```markdown
Hello, I am trying to build golang module and I need these packages to be included in this module:

 * hostname
   * dependency of:
     * golang
 * perl
   * dependency of:
     * golang
```


## API

### Description

This section contains list of provided packages. In case the package deviates
from the package provided in standard Fedora repositories, there is a
description provided which explains the deviation, example:

### common-build-dependencies

 * `hostname`


### common-build-dependencies-bootstrap

 * `autoconf`
   * doesn't provide files for emacs
   * doesn't run test-suite
   * doesn't provide documentation


## Requests


### Description

Put requests for packages you require in the `common-build-dependencies` module here via pull request.


### Prioritized list

This list is sorted by priority.

 * `help2man`
   * common build dependency for GNU projects
   * dependency of:
     * `autoconf`

 * `emacs`
   * dependency of:
     * `autoconf`
     * `automake` (test suite)

 * `erlang`
   * dependency of:
     * `autoconf`

 * `libtool`
   * dependency of:
     * `automake` (test suite)

 * `libevent`
   * dependency of:
     * `memcached`
