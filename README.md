<img src="https://duckdb.org/images/DuckDB_Logo_dl.png" height="50">

# duckdb R package

## Installation from CRAN

```r
install.packages("duckdb")
```

## Building

The default build compiles a release version from an amalgamation.

```sh
cd tools/rpkg
R CMD INSTALL .
```

Optional extensions can be enabled by passing them (comma-separated, if there is more than one) to the environment variable `DUCKDB_R_EXTENSIONS`:

```sh
DUCKDB_R_EXTENSIONS=tpch R CMD INSTALL .
```

## Development

For development, setting the `DUCKDB_R_DEBUG` environment variable enables incremental debugging builds for the R package.

```sh
cd tools/rpkg
DUCKDB_R_DEBUG=1 R CMD INSTALL .
```

This also works for devtools:

```r
Sys.setenv(DUCKDB_R_DEBUG = "1")
pkgload::load_all()
```

Add the following to your `.Renviron` to make this the default:

```
DUCKDB_R_DEBUG=1
```

If you do this, remember to use `--vanilla` for building release builds.
