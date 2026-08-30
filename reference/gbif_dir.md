# Default storage location

Default location can be set with the env var GBIF_HOME, otherwise will
use the default provided by
[`tools::R_user_dir()`](https://rdrr.io/r/tools/userdir.html)

## Usage

``` r
gbif_dir()
```

## Value

path to the gbif home directory directory

## Examples

``` r
gbif_dir()
#> [1] "/github/home/.local/share/R/gbif"
```
