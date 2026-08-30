# Return a handle to an existing Virtuoso Process

Generally a user will not need to access this function directly, though
it may be useful for debugging purposes.

## Usage

``` r
vos_process(p = NA)
```

## Arguments

- p:

  a process object, returned by `vos_process()` or
  [`vos_start()`](https://docs.ropensci.org/virtuoso/reference/vos_start.md).
  (will be restored from cache if not provided)

## Value

returns the
[`processx::process()`](http://processx.r-lib.org/reference/process.md)
object cached by
[`vos_start()`](https://docs.ropensci.org/virtuoso/reference/vos_start.md)
to control the external Virtuoso sever process from R.

## Examples

``` r
if(has_virtuoso())
vos_process()
```
