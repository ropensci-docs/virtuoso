# Destroy all Virtuoso's directories

Provides a clean reset of the system that purges all data files, config
files, cache and log files created by virtuoso R package. This does not
uninstall Virtuoso software itself, see
[`vos_uninstall()`](https://docs.ropensci.org/virtuoso/reference/vos_uninstall.md)
to uninstall.

## Usage

``` r
vos_destroy_all(force = FALSE)
```

## Arguments

- force:

  should permissions be changed (if possible) to allow deletion?

## Value

[TRUE](https://rdrr.io/r/base/logical.html) if entirely successful in
removing all files, [FALSE](https://rdrr.io/r/base/logical.html)
otherwise (invisibly).

## Examples

``` r

vos_destroy_all()
```
