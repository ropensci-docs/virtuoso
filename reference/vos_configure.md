# Configure Virtuoso Server ini file

Virtuoso Server configuration is determined by a virtuoso.ini file when
server starts. This file includes both system-specific information from
your install (location of server files, addons, etc) and
user-configurable parameters. This helper function provides a way to
create and modify an appropriate `virtuoso.ini` file.

## Usage

``` r
vos_configure(
  dirs_allowed = getwd(),
  gigs_ram = 2,
  template = find_virtuoso_ini(),
  db_dir = vos_db()
)
```

## Arguments

- dirs_allowed:

  Paths (relative or absolute) to directories from which Virtuoso should
  have read and write access (e.g. for bulk uploading). Should be
  specified as a single comma-separated string.

- gigs_ram:

  Indicate approximately the maximum GB of memory Virtuoso can have
  access to. (Used to set NumberOfBuffers & MaxDirtyBuffers in config.)

- template:

  Location of an existing virtuoso.ini file which will be used as a
  template. By default, `vos_configure()` will attempt to locate the
  appropriate template for your system.

- db_dir:

  location where `virtuoso.ini` file should be written. Other Virtuoso
  database log files will also be written here.

## Value

Writes the requested `virtuoso.ini` file to the db_dir specified and
returns the path to this file.

## References

<http://docs.openlinksw.com/virtuoso/dbadm/>

## Examples

``` r
# \donttest{
# can take > 5s to test
## configure with typical defaults:
vos_configure()
#> Warning: Exiting, virtuoso template not found... is virtuoso installed?
## Increase or decrease RAM available to virtuoso:
vos_configure(gigs_ram = 1)
#> Warning: Exiting, virtuoso template not found... is virtuoso installed?
# }
```
