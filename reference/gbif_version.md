# Get the latest gbif version string

Can also return latest locally downloaded version, or list all versions

## Usage

``` r
gbif_version(
  local = FALSE,
  dir = gbif_dir(),
  bucket = gbif_default_bucket(),
  all = FALSE,
  ...
)
```

## Arguments

- local:

  Search only local versions? logical, default `FALSE`.

- dir:

  local directory
  ([`gbif_dir()`](https://docs.ropensci.org/gbifdb/reference/gbif_dir.md))

- bucket:

  Which remote bucket (region) should be checked

- all:

  show all versions? (logical, default `FALSE`)

- ...:

  additional arguments to
  [arrow::s3_bucket](https://arrow.apache.org/docs/r/reference/s3_bucket.html)

## Value

latest available gbif version, string

## Details

A default version can be set using option `gbif_default_version`

## Examples

``` r
## Latest local version available:
gbif_version(local=TRUE)
#> [1] "-Inf"
## default version
options(gbif_default_version="2021-01-01")
gbif_version()
#> [1] "2021-01-01"
if (FALSE) { # interactive()
## Latest online version available:
gbif_version()
## All online versions:
gbif_version(all=TRUE)
}
```
