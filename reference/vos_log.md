# Query the server logs

Query the server logs

## Usage

``` r
vos_log(p = NA, collapse = NULL, just_errors = FALSE)
```

## Arguments

- p:

  a process object, returned by
  [`vos_process()`](https://docs.ropensci.org/virtuoso/reference/vos_process.md)
  or
  [`vos_start()`](https://docs.ropensci.org/virtuoso/reference/vos_start.md).
  (will be restored from cache if not provided)

- collapse:

  an optional character string to separate the lines in a single
  character string.

- just_errors:

  logical, default [FALSE](https://rdrr.io/r/base/logical.html). Set to
  [TRUE](https://rdrr.io/r/base/logical.html) to return just the lines
  that contain the term "error", which can be useful in debugging or
  validating bulk imports.

## Value

Virtuoso logs as a character vector.

## See also

[`vos_start()`](https://docs.ropensci.org/virtuoso/reference/vos_start.md)

## Examples

``` r
if(has_virtuoso())
  vos_log()
```
