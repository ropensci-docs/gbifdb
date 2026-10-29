# gbifdb: High Performance Interface to 'GBIF'

A high performance interface to the Global Biodiversity Information
Facility, 'GBIF'. In contrast to 'rgbif', which can access small subsets
of 'GBIF' data through web-based queries to a central server, 'gbifdb'
provides enhanced performance for R users performing large-scale
analyses on servers and cloud computing providers, providing full
support for arbitrary 'SQL' or 'dplyr' operations on the complete 'GBIF'
data tables (now over 1 billion records, and over a terabyte in size).
'gbifdb' accesses a copy of the 'GBIF' data in 'parquet' format, which
is already readily available in commercial computing clouds such as the
Amazon Open Data portal and the Microsoft Planetary Computer, or can be
accessed directly without downloading, or downloaded to any server with
suitable bandwidth and storage space. The high-performance techniques
for local and remote access are described in
<https://duckdb.org/why_duckdb> and
<https://arrow.apache.org/docs/r/articles/fs.html> respectively.

## See also

Useful links:

- <https://docs.ropensci.org/gbifdb/>

- <https://github.com/ropensci/gbifdb>

- Report bugs at <https://github.com/ropensci/gbifdb>

## Author

**Maintainer**: Carl Boettiger <cboettig@gmail.com>
([ORCID](https://orcid.org/0000-0002-1642-628X))

Other contributors:

- Marc-Olivier Beausoleil <marc-olivier.beausoleil@mail.mcgill.ca>
  ([ORCID](https://orcid.org/0000-0003-3717-3223)) \[contributor\]
