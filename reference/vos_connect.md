# Connect to a Virtuoso Server over ODBC

Connect to a Virtuoso Server over ODBC

## Usage

``` r
vos_connect(
  driver = NULL,
  uid = "dba",
  pwd = "dba",
  host = "localhost",
  port = "1111",
  system_odbcinst = find_odbcinst(),
  local_odbcinst = odbcinst_path()
)
```

## Arguments

- driver:

  Name of the Driver line in the ODBC configuration

- uid:

  User id. Defaults to "dba"

- pwd:

  Password. Defaults to "dba"

- host:

  IP address of the Virtuoso Server

- port:

  Port used by Virtuoso. Defaults to the Virtuoso standard port, 1111

- system_odbcinst:

  Path to the system `odbcinst.ini` file. (Does not require write
  access.) Default will attempt to find the file for your system.

- local_odbcinst:

  Path to the local odbcinst we should use.

## Value

a DBI connection to the Virtuoso database. This can be passed to
additional virtuoso functions such as
[`vos_import()`](https://docs.ropensci.org/virtuoso/reference/vos_import.md)
or
[`vos_query()`](https://docs.ropensci.org/virtuoso/reference/vos_query.md),
and can also be used as a standard DBI or dplyr database backend.

## Details

Default parameters are appropriate for the automatic installer provided
by the package and for the default settings typically used by local
Virtuoso installers. Adjust these only if you are connecting to a remote
virtuoso server that is not controlled from the R package.

## See also

[`vos_install()`](https://docs.ropensci.org/virtuoso/reference/vos_install.md),
[`vos_start()`](https://docs.ropensci.org/virtuoso/reference/vos_start.md)

## Examples

``` r
status <- vos_status()
#> virtuoso isn't running.
# \donttest{
if(has_virtuoso()){
## start up
vos_start()
con <- vos_connect()
}
# }
```
