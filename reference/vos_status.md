# Query the server status

Query the server status

## Usage

``` r
vos_status(p = NA, wait = 10)
```

## Arguments

- p:

  a process object, returned by
  [`vos_process()`](https://docs.ropensci.org/virtuoso/reference/vos_process.md)
  or
  [`vos_start()`](https://docs.ropensci.org/virtuoso/reference/vos_start.md).
  (will be restored from cache if not provided)

- wait:

  number of seconds to wait for server to come online

## Value

a character string indicating the state of the server:

- "not detected" if no process can be found

- "dead" process exists but reports that server is not alive. Server may
  fail to come online due to errors in configuration file. see
  [`vos_configure()`](https://docs.ropensci.org/virtuoso/reference/vos_configure.md)

- "running" Server is up and accepting queries.

- "sleeping" Server is up and accepting queries.

## Details

Note: Use
[`vos_log()`](https://docs.ropensci.org/virtuoso/reference/vos_log.md)
to see the full log

## Examples

``` r
if(has_virtuoso())
  vos_status()
```
