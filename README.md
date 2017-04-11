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
 * `golang`
   * doesn't run on ppc64
   * compiled with gcc-go


## Requests


### Description

Put requests for packages you require in the `common-build-dependencies` module here via pull request.

### Prioritized list

This list is sorted by priority.

 * `texinfo`
   * build-requires plenty of perl packages which are not available yet
   * dependency of:
     * `libtool`

 * `libtool`
   * dependency of:
     * `automake` (test suite)
     * `php`

 * `cmake`
   * dependency of:
     * `ruby`
     * `docker`

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
     * `python3`
     * `bind`
     * `ruby`

 * `automake`
   * dependency of:
     * `dhcp-server`

 * multilib-rpm-config
   * dependency of:
     * `mariadb`
     * `ruby`

 * `help2man`
   * common build dependency for GNU projects
   * dependency of:
     * `autoconf`

 * `golang`
   * dependency of:
     * `docker`


## Unknown

It is unknown to me where should be these packages placed

 * `selinux-policy`
   * dependency of:
     * `mariadb`
 * `python-pymongo`
   * dependency of:
     * `mongodb`
 * `exim`
   * dependency of:
     * `php`
 * `net-snmp`
   * dependency of:
     * `php`
 * `opensmtpd`
   * dependency of:
     * `php`
 * `sendmail`
   * dependency of:
     * `php`
 * `uw-imap`
   * dependency of:
     * `php`


## Unprocessed

Ready for procesing.


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
     * `php`
 * `libaio`
   * should be placed to shared-userspace
   * dependency of:
     * `mariadb`
 * `libedit`
   * should be placed to shared-userspace
   * dependency of:
     * `mariadb`
     * `php`
 * `valgrind`
   * should be part of C runtime module
   * dependency of:
     * `mongodb`
     * `python3`
 * `boost`
   * part of shared-userspace
   * dependency of:
     * `mongodb`
 * `gcc`
   * part of C runtime module
   * part of base-runtime
   * dependency of:
     * `mongodb`
     * `nodejs`
 * `icu`
   * part of shared-userspace
   * dependency of:
     * `mongodb`
     * `nodejs`
     * `php`
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
     * `python3`
 * `findutils`
   * should be part of shared-userspace
   * dependency of:
     * `python2`
 * `libX11`
   * should be part of shared-userspace
   * dependency of:
     * `python2`
     * `python3`
 * `mesa`
   * should be part of shared-userspace
   * dependency of:
     * `python2`
     * `python3`
 * `valgrind`
   * should be part of debug tools or C runtime
   * dependency of:
     * `python2`
 * `tcl, tix, tk`
   * shared-userspace?
   * dependency of:
     * `python2`
     * `python3`
 * `compat-openssl10`
   * should be part of debug tools or C runtime
   * dependency of:
     * `mariadb`
     * `python2`
     * `nodejs`
 * `bluez`
   * should be part of shared-userspace
   * dependency of:
     * `python3`
 * `libdb4`
   * should be part of shared-userspace
   * dependency of:
     * `python3`
 * `systemtap`
   * should be part of debug tools or this module
   * dependency of:
     * `python3`
     * `ruby`
 * `libuv`
   * should be part of shared-userspace
   * dependency of:
     * `nodejs`
 * `docbook-style-xsl`
   * should be part of shared-userspace
   * dependency of:
     * `bind`
 * `GeoIP`
   * should be part of shared-userspace
   * dependency of:
     * `bind`
 * `mariadb`
   * part of mariadb module
   * dependency of:
     * `bind`
     * `postfix`
 * `python3`
   * part of python3 module
   * dependency of:
     * `bind`
 * `postgresql`
   * part of postgresql module
   * dependency of:
     * `bind`
     * `php`
     * `postfix`
 * `checksec`
   * should be part of shared-userspace
   * dependency of:
     * `ruby`
 * `libyaml`
   * part of shared-userspace
   * dependency of:
     * `ruby`
 * `aspell`
   * should be part of shared-userspace
   * dependency of:
     * `php`
 * `curl`
   * part of base-runtime
   * dependency of:
     * `php`
 * `enchant`
   * should be part of shared-userspace
   * dependency of:
     * `php`
 * `firebird`
   * should be part of shared-userspace
   * dependency of:
     * `php`
 * `freetds`
   * should be part of shared-userspace
   * dependency of:
     * `php`
 * `gd`
   * should be part of shared-userspace
   * dependency of:
     * `php`
 * `httpd`
   * part of httpd module
   * dependency of:
     * `php`
 * `libmcrypt`
   * should be part of shared-userspace
   * dependency of:
     * `php`
 * `libmcrypt`
   * should be part of shared-userspace
   * dependency of:
     * `php`
 * `libxml2`
   * should be part of shared-userspace
   * dependency of:
     * `php`
 * `libxslt`
   * should be part of shared-userspace
   * dependency of:
     * `php`
 * `nginx`
   * part of nginx module
   * dependency of:
     * `php`
 * `postfix`
   * part of postfix module
   * dependency of:
     * `php`
 * `unixODBC`
   * should be part of shared-userspace
   * dependency of:
     * `php`
 * `sqlite`
   * should be part of shared-userspace
   * dependency of:
     * `php`
     * `docker`
 * `recode`
   * should be part of shared-userspace
   * dependency of:
     * `php`
 * `tidy`
   * should be part of shared-userspace
   * dependency of:
     * `php`
 * `tokyocabinet`
   * should be part of shared-userspace
   * dependency of:
     * `php`
 * `btrfs-progs`
   * should be part of shared-userspace
   * dependency of:
     * `docker`
 * `device-mapper`
   * should be part of shared-userspace
   * dependency of:
     * `docker`
 * `git`
   * should be part of shared-userspace
   * dependency of:
     * `docker`
 * `godep`
   * should be part of shared-userspace
   * dependency of:
     * `docker`
 * `golang-github-cpuguy83-go-md2man`
   * should be part of shared-userspace
   * dependency of:
     * `docker`
 * `tinycdb`
   * dependency of:
     * `postfix`
 * `postgresql`
   * dependency of:
     * `postfix`


## Invalid requests

I was not able to track these packages.

 * `asio`
   * dependency of:
     * `mongodb`


## TODO

 * get rid of `should be`
 * get rid of unknowns
