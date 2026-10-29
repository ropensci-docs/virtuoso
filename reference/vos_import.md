# Bulk Import of RDF triples

While triples data can be added one by one over SPARQL queries, Virtuoso
bulk import is by far the fastest way to import large triplestores in
the database.

## Usage

``` r
vos_import(
  con,
  files = NULL,
  wd = ".",
  glob = "*",
  graph = "rdflib",
  n_cores = 1L
)
```

## Arguments

- con:

  a ODBC connection to Virtuoso, from
  [`vos_connect()`](https://docs.ropensci.org/virtuoso/reference/vos_connect.md)

- files:

  paths to files to be imported

- wd:

  Alternatively, can specify directory and globbing pattern to import.
  Note that in this case, wd must be in (or a subdir of) the
  `AllowedDirs` list of `virtuoso.ini` file created by
  [`vos_configure()`](https://docs.ropensci.org/virtuoso/reference/vos_configure.md).
  By default, this includes the working directory where you called
  [`vos_start()`](https://docs.ropensci.org/virtuoso/reference/vos_start.md)
  or
  [`vos_configure()`](https://docs.ropensci.org/virtuoso/reference/vos_configure.md).

- glob:

  A wildcard aka globbing pattern (e.g. \`"\*.nq"“).

- graph:

  Name (technically URI) for a graph in the database. Can leave as
  default. If a graph is already specified by the import file (e.g. in
  nquads), that will be used instead.

- n_cores:

  specify the number of available cores for parallel loading.
  Particularly useful when importing large numbers of bulk files.

## Value

(Invisibly) returns the status table of the bulk loader, indicating file
loading time or errors.

## Details

the bulk importer imports all files matching a pattern in a given
directory. If given a list of files, these are temporarily symlinked (or
copied on Windows machines) to the Virtuoso app cache dir in a
subdirectory, and the entire subdirectory is loaded (filtered by the
globbing pattern). If files are not specified, load is called directly
on the specified directory and pattern. This is particularly useful for
loading large numbers of files.

Note that Virtuoso recommends breaking large files into multiple smaller
ones, which can improve loading time (particularly if using multiple
cores.)

Virtuoso Bulk Importer recognizes the following file formats:

- `.grdf`

- `.nq`

- `.owl`

- `.nt`

- `.rdf`

- `.trig`

- `.ttl`

- `.xml`

Any of these can optionally be gzipped (with a `.gz` extension).

## References

<http://vos.openlinksw.com/owiki/wiki/VOS/VirtBulkRDFLoader>

## Examples

``` r

vos_status()
#> virtuoso isn't running.

# \donttest{
if(has_virtuoso()){
vos_start()
con <- vos_connect()

example <- system.file("extdata", "person.nq", package = "virtuoso")
vos_import(con, example)
}
# }
```
