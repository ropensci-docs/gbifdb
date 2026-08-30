# Local connection to a downloaded GBIF Parquet database

Local connection to a downloaded GBIF Parquet database

## Usage

``` r
gbif_local(
  dir = gbif_parquet_dir(version = gbif_version(local = TRUE)),
  tblname = "gbif",
  backend = c("arrow", "duckdb"),
  safe = TRUE
)
```

## Arguments

- dir:

  location of downloaded GBIF parquet files

- tblname:

  name for the database table

- backend:

  choose duckdb or arrow.

- safe:

  logical. Should we exclude columns `mediatype` and `issue`? (default
  `TRUE`). varchar datatype on these columns substantially slows downs
  queries.

## Value

a remote tibble `tbl_sql` class object

## Details

A summary of this GBIF data, along with column meanings can be found at
<https://github.com/gbif/occurrence/blob/master/aws-public-data.md>

## Examples

``` r
if (FALSE) { # interactive()

gbif <- gbif_local(gbif_example_data())
}
```
