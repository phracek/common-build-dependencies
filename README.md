# common-build-dependencies

`common-build-dependencies` contains packages to build other packages. Runtime
dependencies should be placed into
[shared-userspace](http://pkgs.fedoraproject.org/cgit/modules/shared-userspace.git/).
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
 * `help2man`
 * `multilib-rpm-config`


### common-build-dependencies-bootstrap

 * `autoconf`
   * doesn't provide files for emacs
   * doesn't run test-suite
   * doesn't provide documentation
 * `automake`
   * doesn't run test-suite
   * doesn't provide documentation


## Requests


### Description

Put requests for packages you require in the `common-build-dependencies` module here via pull request.

### Prioritized list

This list is sorted by priority.

 * `libtool`
   * dependency of:
     * `automake` (test suite)

 * `doxygen`
   * dependency of:
     * `dhcp-server`

 * `scons`
   * dependency of:
     * `mongodb`

 * `emacs`
   * dependency of:
     * `autoconf`
     * `automake` (test suite)

 * `erlang`
   * dependency of:
     * `autoconf`


## Done

This is a list of packages which are already done. Feel free to update the
dependency tree.

 * `autoconf`
   * dependency of:
     * `dhcp-server`
     * `python2`

 * `automake`
   * dependency of:
     * `dhcp-server`

 * multilib-rpm-config
   * dependency of:
     * `mariadb`

 * `help2man`
   * common build dependency for GNU projects
   * dependency of:
     * `autoconf`


## Unknown

It is unknown to me where should be these packages placed

 * `selinux-policy`
   * dependency of:
     * `mariadb`
 * `python-pymongo`
   * dependency of:
     * `mongodb`


## Unprocessed

Ready for procesing.



 * `python3`
   * build dependencies:
     * `autoconf bluez expat libdb4 libX11 mesa systemtap tcl tix tk valgrind`
   * runtime dependecies: 
     * `python3`

 * `nodejs`
	  * build dependencies:
        * `compat-openssl10 gcc icu libuv`
    * runtime dependencies:
	     * `libuv`
 * `PHP`
    * build dependecies:
      * `aspell curl enchant exim firebird freetds gd httpd icu libedit libmcrypt libtool libxml2 libxslt net-snmp nginx opensmtpd pcre postfix postgresql recode sendmail sqlite tidy tokyocabinet unixODBC uw-imap`
    * runtime dependecies:
       * php

 * `ruby`
   * build dependecies:
     * `autoconf checksec cmake libyaml multilib-rpm-config systemtap`
   * runtime dependecies:
     * `ruby rubypick`

 * `bind`
   * build dependecies:
     * `autoconf docbook-style-xsl GeoIP mariadb postgresql python3`
   * runtime dependecies:
     * `bind`


## Denied requests

Packages bellow are here for tracking purposes. None of them belong to this
module and should be placed elsewhere.

 * `bind99`
   * dependency of:
     * `dhcp-server`
 * `perl-generators`
   * part of perl module
   * dependency of:
     * `mariadb`
 * `pcre`
   * part of base-runtime
   * dependency of:
     * `mariadb`
 * `libaio`
   * should be placed to shared-userspace
   * dependency of:
     * `mariadb`
 * `libedit`
   * should be placed to shared-userspace
   * dependency of:
     * `mariadb`
 * `valgrind`
   * should be part of C runtime module
   * dependency of:
     * `mongodb`
 * `boost`
   * part of shared-userspace
   * dependency of:
     * `mongodb`
 * `gcc`
   * part of C runtime module
   * part of base-runtime
   * dependency of:
     * `mongodb`
 * `icu`
   * part of shared-userspace
   * dependency of:
     * `mongodb`
 * `snappy`
   * part of shared-userspace
   * dependency of:
     * `mongodb`
 * `gperftools`
   * should be part of shared-userspace
   * dependency of:
     * `mongodb`
 * `libstemmer`
   * should be part of shared-userspace
   * dependency of:
     * `mongodb`
 * `yaml-cpp`
   * should be part of shared-userspace
   * dependency of:
     * `mongodb`
 * `yaml-cpp03`
   * should be part of shared-userspace
   * dependency of:
     * `mongodb`
 * `expat`
   * should be part of shared-userspace
   * dependency of:
     * `python2`
 * `findutils`
   * should be part of shared-userspace
   * dependency of:
     * `python2`
 * `libX11`
   * should be part of shared-userspace
   * dependency of:
     * `python2`
 * `mesa`
   * should be part of shared-userspace
   * dependency of:
     * `python2`
 * `valgrind`
   * should be part of debug tools or C runtime
   * dependency of:
     * `python2`
 * `tcl, tix, tk`
   * shared-userspace?
   * dependency of:
     * `python2`
 * `compat-openssl10 `
   * dependency of:
     * `mariadb`
     * `python2`


## Invalid requests

I was not able to track these packages.

 * `asio`
   * dependency of:
     * `mongodb`
