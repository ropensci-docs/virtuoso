# Stop (kill) the Virtuoso server

Kill ends the process started by
[`vos_start()`](https://docs.ropensci.org/virtuoso/reference/vos_start.md)

## Usage

``` r
vos_kill(p = NA)
```

## Arguments

- p:

  a process object, returned by
  [`vos_process()`](https://docs.ropensci.org/virtuoso/reference/vos_process.md)
  or
  [`vos_start()`](https://docs.ropensci.org/virtuoso/reference/vos_start.md).
  (will be restored from cache if not provided)

## Details

vos_kill simply shuts down the local Virtuoso server, it does not remove
any data stored in the database system. `vos_kill()` terminates the
process, removing the process id from the process table.

## See also

[`vos_start()`](https://docs.ropensci.org/virtuoso/reference/vos_start.md)

## Examples

``` r
# \donttest{
if(has_virtuoso()){

  vos_start()
  vos_kill()

  }
# }
```
