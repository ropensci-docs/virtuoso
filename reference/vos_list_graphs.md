# List graphs

List graphs

## Usage

``` r
vos_list_graphs(con)
```

## Arguments

- con:

  a ODBC connection to Virtuoso, from
  [`vos_connect()`](https://docs.ropensci.org/virtuoso/reference/vos_connect.md)

## Examples

``` r
status <- vos_status()
#> virtuoso isn't running.
# \donttest{
if(has_virtuoso() & is.null(status)){
vos_start()
con <- vos_connect()
vos_list_graphs(con)

}# }
```
