# virtuoso: An R Interface to Virtuoso Using ODBC

Virtuoso is a high-performance "universal server," which can act as both
a relational database (supporting standard SQL queries), and an Resource
Description Framework (RDF) triplestore, supporting SPARQL queries and
semantic reasoning. The `virtuoso` R package provides R users with a
DBI-compatible connection to the Virtuoso database. The package also
provides helper routines to install, launch, and manage a Virtuoso
server locally on Mac, Windows and Linux platforms using the standard
interactive installers from the R command-line. By automatically
handling these setup steps, the package can make Virtuoso considerably
faster and easier for a most users to deploy in a local environment.
While this can be used as a normal `dplyr` backend, Virtuoso excels when
used as a RDF triplestore. Managing the bulk import of triples from
common serializations with a single intuitive command is another key
feature of the `virtuoso` R package. Bulk import performance can be tens
to hundreds of times faster than the comparable imports using existing R
tools, including `rdflib` and `redland` packages.

## See also

Useful links:

- <https://github.com/ropensci/virtuoso>

- Report bugs at <https://github.com/ropensci/virtuoso/issues>

## Author

**Maintainer**: Carl Boettiger <cboettig@gmail.com>
([ORCID](https://orcid.org/0000-0002-1642-628X)) \[copyright holder\]

Other contributors:

- Bryce Mecum <brycemecum@gmail.com>
  ([ORCID](https://orcid.org/0000-0002-0381-3766)) \[contributor\]
