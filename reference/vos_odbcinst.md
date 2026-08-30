# Configure the ODBC Driver for Virtuoso

ODBC uses an `odbcinst.ini` file to point ODBC at the library required
to drive any given database. This function helps us automatically locate
the driver library on different operating systems and configure the
odbcinst appropriately for each OS.

## Usage

``` r
vos_odbcinst(
  system_odbcinst = find_odbcinst(),
  local_odbcinst = odbcinst_path()
)
```

## Arguments

- system_odbcinst:

  Path to the system `odbcinst.ini` file. (Does not require write
  access.) Default will attempt to find the file for your system.

- local_odbcinst:

  Path to the local odbcinst we should use.

## Value

the path to the odbcinst file that is created or modified.

## Details

This function is called automatically by
[`vos_install()`](https://docs.ropensci.org/virtuoso/reference/vos_install.md)
and thus does not usually need to be called by the user. Users can also
manually configure ODBC as outlined in
<https://github.com/r-dbi/odbc#dsn-configuration-files>. This is merely
a convenience function automating that process on most systems.

## Examples

``` r
# \donttest{
## Configures ODBC and returns silently on success.
vos_odbcinst()
#> Warning: could not automatically locate virtodbc.so

## see where the inst file is located:
inst <- vos_odbcinst()
inst
#> /tmp/RtmpSnyX7o/vos/config/odbcinst.ini
# }
```
