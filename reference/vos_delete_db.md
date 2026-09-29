# Delete Virtuoso Database

delete the entire Virtuoso database for a fresh start.

## Usage

``` r
vos_delete_db(ask = is_interactive(), db_dir = vos_db())
```

## Arguments

- ask:

  ask before deleting?

- db_dir:

  location of the directory to delete

## Examples

``` r

vos_delete_db()
```
