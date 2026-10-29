# Download GBIF data using minioclient

Sync a local directory with selected release of the AWS copy of GBIF

## Usage

``` r
gbif_download(
  version = gbif_version(),
  dir = gbif_dir(),
  bucket = gbif_default_bucket(),
  region = ""
)
```

## Arguments

- version:

  Release date (YYYY-MM-DD) which should be synced. Will detect latest
  version by default.

- dir:

  path to local directory where parquet files should be stored. Fine to
  leave at default, see
  [`gbif_dir()`](https://docs.ropensci.org/gbifdb/reference/gbif_dir.md).

- bucket:

  Name of the regional S3 bucket desired. Default is
  "gbif-open-data-us-east-1". Select a bucket closer to your compute
  location for improved performance, e.g. European researchers may
  prefer "gbif-open-data-eu-central-1" etc.

- region:

  bucket region (usually ignored? Just set the bucket appropriately)

## Value

logical indicating success or failure.

## Details

Sync parquet files from GBIF public data catalog,
https://registry.opendata.aws/gbif/.

Note that data can also be found on the Microsoft Cloud,
https://planetarycomputer.microsoft.com/dataset/gbif

Also, some users may prefer to download this data using an alternative
interface or work on a cloud-host machine where data is already
available. Note, these data include all CC0, CC-BY and CC-BY-NC licensed
data in GBIF. The data snapshot description and dataset details is
available at this link:
<https://github.com/gbif/occurrence/blob/master/aws-public-data.md>.

## Examples

``` r
if (FALSE) { # interactive()
gbif_download()
}
```
