# Start a Virtuoso Server

This function will attempt to start a virtuoso server instance that can
be managed completely from R. This allows the user to easily start,
stop, and access server logs and functions from the R command line. This
server will be automatically shut down when R exits or restarts, or can
be explicitly controlled using
[`vos_kill()`](https://docs.ropensci.org/virtuoso/reference/vos_kill.md),
[`vos_log()`](https://docs.ropensci.org/virtuoso/reference/vos_log.md),
and
[`vos_status()`](https://docs.ropensci.org/virtuoso/reference/vos_status.md).

## Usage

``` r
vos_start(ini = NULL, wait = 30)
```

## Arguments

- ini:

  path to a virtuoso.ini configuration file. If not provided, function
  will attempt to determine the location of the default configuration
  file.

- wait:

  number of seconds to wait for server to come online

## Value

invisibly returns the
[`processx::process()`](http://processx.r-lib.org/reference/process.md)
object which can be used to control the external process from R. It is
not necessary for a user to store this return object, as `vos_start()`
caches the process object so it can be automatically accessed by other
functions without needing to store and pass the return object.

## Details

It can take some time for the server to come up before it is ready to
accept queries. `vos_start()` will return as soon as the server is
active, which typically takes about 10 seconds on tested systems.
`vos_start()` monitors the Virtuoso logs every one second for a maximum
time of `wait` seconds (default 30 seconds) to see if the server is
ready. If `wait` time is exceeded, `vos_start()` will simply return the
current server status. This does not mean that starting has failed, it
may simply need longer before the server is active. Use
[`vos_status()`](https://docs.ropensci.org/virtuoso/reference/vos_status.md)
to continue to monitor the server status manually.

If no `virtuoso.ini` configuration file is provided, `vos_start()` will
automatically attempt to configure one. For more control over this, use
[`vos_configure()`](https://docs.ropensci.org/virtuoso/reference/vos_configure.md),
see examples.

## See also

[`vos_install()`](https://docs.ropensci.org/virtuoso/reference/vos_install.md)

## Examples

``` r
# \donttest{

if(has_virtuoso()){
vos_start()
## or with custom config:
vos_start(vos_configure(gigs_ram = 3))

}
# }
```
