# set Virtuoso paths

Set the location of Virtuoso database, configure files, cache, and logs
to your preferred location. Set home to the location of your Virtuoso
installation.

## Usage

``` r
vos_set_paths(
  db_dir = vos_db(),
  config_dir = vos_config(),
  cache_dir = vos_cache(),
  log_dir = vos_logdir(),
  home = virtuoso_home()
)
```

## Arguments

- db_dir:

  Location of data in the Virtuoso (tables, triplestore)

- config_dir:

  Location of configuration files for Virtuoso

- cache_dir:

  Location of cache for bulk importing

- log_dir:

  Location of Virutoso Server logs

- home:

  Location of the Virtuoso installation

## Value

A logical vector, with elements being true if setting the corresponding
variable succeeded (invisibly).

## Examples

``` r
if(has_virtuoso())
  vos_set_paths()
```
