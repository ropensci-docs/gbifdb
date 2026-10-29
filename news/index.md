# Changelog

## gbifdb 1.0.0.99

- updated description for
  [`gbif_download()`](https://docs.ropensci.org/gbifdb/reference/gbif_download.md)
  function explaining the current license in the snapshot (see
  <https://github.com/ropensci/gbifdb/issues/13>)

## gbifdb 1.0.0

CRAN release: 2023-10-19

- [`gbif_download()`](https://docs.ropensci.org/gbifdb/reference/gbif_download.md)
  now uses `minioclient` as a backend, offering dramatically (100x+)
  better performance, especially on multi-core machines with high
  bandwidth network connections.

- [`gbif_local()`](https://docs.ropensci.org/gbifdb/reference/gbif_local.md)
  now defaults to duckdb backend, and utilizes duckdbfs to streamline
  the interface. The latest performance of `duckdb` is substantially
  better than alternatives.

Breaking changes

- `gbif_conn()` is deprecated

## gbifdb 0.1.2

CRAN release: 2022-05-21

- include links in DESCRIPTION to the unpublished methods implemented in
  arrow and duckdb for high-performance access.
- update documentation to include return value on all exported
  functions.

## gbifdb 0.1.1

- Automatically detect latest release (see
  [`gbif_version()`](https://docs.ropensci.org/gbifdb/reference/gbif_version.md)).
  Works with local and remote sources, can also report all available
  versions.
- add
  [`gbif_local()`](https://docs.ropensci.org/gbifdb/reference/gbif_local.md)
  to return a remote table instead of a connection; paralleling the use
  of
  [`gbif_remote()`](https://docs.ropensci.org/gbifdb/reference/gbif_remote.md)
- `gbif_conn()` (and thus
  [`gbif_local()`](https://docs.ropensci.org/gbifdb/reference/gbif_local.md)
  ) gain the ability to use arrow as a backend to duckdb, and this is
  now the default. This improves performance and avoids crashes when all
  columns are requested.
- default bucket set to “us-east-1” (across both
  [`gbif_download()`](https://docs.ropensci.org/gbifdb/reference/gbif_download.md)
  and
  [`gbif_remote()`](https://docs.ropensci.org/gbifdb/reference/gbif_remote.md))
- [`gbif_download()`](https://docs.ropensci.org/gbifdb/reference/gbif_download.md)
  now automatically detects versions, downloads parquet files to a path
  that parallels the remote path (using release-specific
  subdirectories), and allows bucket to be configured.
- set `to_duckdb=TRUE` by default in
  [`gbif_remote()`](https://docs.ropensci.org/gbifdb/reference/gbif_remote.md),
  creating a consistent lazy-table interface with support for windowed
  functions
- `gbif_conn()` (and
  [`gbif_local()`](https://docs.ropensci.org/gbifdb/reference/gbif_local.md))
  now automatically detect the path of most recent GBIF version in
  [`gbif_dir()`](https://docs.ropensci.org/gbifdb/reference/gbif_dir.md).
  No more need to to manually set path for `occurrence.parquet/`
  subfolder.
- documentation improved.
