# common-build-depedencies

This is likely be the module, which you need to require in order to build your module.


## Workflow

If you need to add a package to this module, please open a pull request and add a new entry to section **Requests**.

Example:

```markdown
 * `emacs`
   * dependency of:
     * `git`
```


## API

### Description

This section will contain list of provided packages. In case the package deviates from the package provided in standard Fedora repositories, there is a description provided which explains the deviation, example:

```
 * `automake`
   * doesn't provide documentation
   * no support for systemtap probes
```


### Provided packages

 * `<EMPTY>`


## Requests

 * `srpm_package_name`
   * dependency of:
     * `package 1`
     * `package 2`

