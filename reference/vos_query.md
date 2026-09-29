# Run a SPARQL query

Run a SPARQL query

## Usage

``` r
vos_query(con, query)
```

## Arguments

- con:

  a ODBC connection to Virtuoso, from
  [`vos_connect()`](https://docs.ropensci.org/virtuoso/reference/vos_connect.md)

- query:

  a SPARQL query statement

## Value

a `data.frame` containing the results of the query

## Details

SPARQL is a graph query language similar in syntax SQL, but allows the
use of variables to walk through graph nodes.

## References

- <https://en.wikipedia.org/wiki/SPARQL>

- <https://docs.ropensci.org/rdflib/articles/rdf_intro.html>

## See also

[`vos_start()`](https://docs.ropensci.org/virtuoso/reference/vos_start.md),
[`vos_connect()`](https://docs.ropensci.org/virtuoso/reference/vos_connect.md)

## Examples

``` r
vos_status()
#> virtuoso isn't running.
# \donttest{
if(has_virtuoso()){
vos_start()
con <- vos_connect()

# show first 4 triples in the database
DBI::dbGetQuery(con, "SPARQL SELECT * WHERE { ?s ?p ?o } LIMIT 4")
}
# }
```
