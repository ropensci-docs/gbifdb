# gbif remote

Connect to GBIF remote directly. Can be much faster than downloading for
one-off use or when using the package from a server in the same region
as the data. See Details.

## Usage

``` r
gbif_remote(
  version = gbif_version(),
  bucket = gbif_default_bucket(),
  safe = TRUE,
  unset_aws = getOption("gbif_unset_aws", TRUE),
  endpoint_override = Sys.getenv("AWS_S3_ENDPOINT", "s3.amazonaws.com"),
  backend = c("arrow", "duckdb"),
  ...
)
```

## Arguments

- version:

  GBIF snapshot date

- bucket:

  GBIF bucket name (including region). A default can also be set using
  the option `gbif_default_bucket`, see
  [options](https://rdrr.io/r/base/options.html).

- safe:

  logical, default TRUE. Should we exclude columns `mediatype` and
  `issue`? varchar datatype on these columns substantially slows downs
  queries.

- unset_aws:

  Unset AWS credentials? GBIF is provided in a public bucket, so
  credentials are not needed, but having a AWS_ACCESS_KEY_ID or other
  AWS environmental variables set can cause the connection to fail. By
  default, this will unset any set environmental variables for the
  duration of the R session. This behavior can also be turned off
  globally by setting the option `gbif_unset_aws` to FALSE (e.g. to use
  an alternative network endpoint)

- endpoint_override:

  optional parameter to
  [`arrow::s3_bucket()`](https://arrow.apache.org/docs/r/reference/s3_bucket.html)

- backend:

  duckdb or arrow

- ...:

  additional parameters passed to the
  [`arrow::s3_bucket()`](https://arrow.apache.org/docs/r/reference/s3_bucket.html)

## Value

a remote tibble `tbl_sql` class object.

## Details

Query performance is dramatically improved in queries that return only a
subset of columns. Consider using explicit
[`select()`](https://dplyr.tidyverse.org/reference/select.html) commands
to return only the columns you need.

A summary of this GBIF data, along with column meanings can be found at
<https://github.com/gbif/occurrence/blob/master/aws-public-data.md>

## Examples

``` r
if (FALSE) { # interactive()

gbif <- gbif_remote()
gbif()
}
```
