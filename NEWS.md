# eurostat 3.7.10 (2022-02-09)

* Fixed URL issues in tests and examples

# eurostat 3.7.9 (2020-10-01)

* Function documentation migrated from old `\code{}`, `\link{}` syntax to markdown (issue #230, PR #231 by @dieghernan)

# eurostat 3.7.8 (2020-09-30)

* Package cache management updated: `options()` command is no longer needed and the cache dir can be modified persistently with a custom function (issue #223, PR #228 by @dieghernan)

# eurostat 3.7.7 (2020-06-24)

* Maps vignette fixed

# eurostat 3.7.6 (2021-05-20)

* Deprecated `add_nuts_level()`, `harmonize_geo_code()`, `recode_to_nuts_2016()` and `recode_to_nuts_2013()`; these functions were moved to the new package regions. The problem of sub-national geo codes is explained in the new vignette "Mapping Regional Data, Mapping Metadata Problems", which replaces the "Regional data  examples for the eurostat R package" vignette. This is a shared vignette, but the new regions package has more articles on how to work with sub-national data. (issues #218 and #219, PR #220 by @antaldaniel)

# eurostat 3.7.5 (2020-05-12)

* Moved sf from Imports to Suggests and made `get_eurostat_geospatial()` return a message if sf is not installed. This is to increase compatibility of eurostat-package on systems that have trouble installing sf (issue #213)
* Wrapped some problem causing examples to `\dontrun{}` for a quick CRAN release

# eurostat 3.7.3

* Removed outdated dependencies (mapproj, plotrix, rsdmx)

# eurostat 3.7.2

* Non-intersecting sf-geometries in get_eurostat_geospatial (PR #202 by @retostauffer)

# eurostat 3.6.4 (2020-05-12)

* Fixed stringsAsFactors for R-4.0.0 and moved default to FALSE

# eurostat 3.6.3 (2020-04-21)

* Stabilized http requests (PR by @annnvv)

# eurostat 3.5.3

* get_eurostat switched to v2.1

# eurostat 3.5.2

* internet and proxy setting fixes
* bibentry fix

# eurostat 3.4.1

* Fixed vignette
* Added automated error messages to URL download failures

# eurostat 3.3.3

* Countries and Country Codes data.frames get label column for country names in the Eurostat database.
* Fixed vignette duplicate entry issue and smaller issues
* Added get_bibentry

# eurostat 3.3.1

* The `label_eurostat()` has new countrycode and countrycode_nomatch arguments to label with countrycode package and custom_dic argument to add custom dictionary.
* Vignette updated

# eurostat 3.2.3

## Minor features

* dplyr moved from Dependencies to Imports
* curl removed from Imports
* solved geospatial map issues
* eurostat_url moved to options

# eurostat 3.2.1

## Major updates

* Improved support for sf in map visualization

## Minor features

* ./data/ generation script in ./data-raw/ updated to make all data reproducible

## Bug fixes

* Typo corrected from Cisco to Gisco

# eurostat 3.1.5

## Minor features

* Added new example data set to reduce repeated downloads from eurostat service
* Now `label_eurostat()` gives always an error by default, if labelling introduces duplicated labels. A new `fix_duplicated` argument is add to fix duplicated labels automatically. (#79, #90)
* Shrinked the package tarball size

## Bug fixes

* Modified tutorial to accommodate the CRAN error
* Fixed cut_to_classes to generate unique breaks

# eurostat 3.1.1

## R Journal submission

* Release version associated with the R Journal manuscript 2017 final version
* Git release added with Zenodo DOI

## Minor features

* Changed maintainer email address from louhos to leo
* Added ./docs/ (automated package website generated with pkgdown)
* Expanded unit tests
* Gitter badge added to README
* Added ./revdep/ to check possible reverse dependencies automatically
* Cheat sheet added

## Bug fixes

* `search_eurostat()` accepts new argument `fixed`: if `TRUE` (default), `pattern` provided will used as is; if `FALSE`, `pattern` will be interpreted as a true regex pattern.
* Augmented the list of Suggested packages in the DESCRIPTION file, including the Cairo package (#70)
* Updated the journal manuscript based on reviewer feedback

# eurostat 2.2.20001

* Development version opened

# eurostat 2.2.1

* Fixed canonical cran url in README

# eurostat 2.1.1

* The complete package now using tibbles
* Rare encoding issues circumvented (#55)
* Improved functionality within firewall-protected systems (#63)

# eurostat 2.0

* The `get_eurostat()` returns tibbles (#52)
* The `get_eurostat_dic()` and `get_eurostat_toc()` return tibbles
* Now `read_tsv()` is used instead of `read.csv()` (#29)

# eurostat 1.2.27

* Calls to extract_numeric are replaced by as.numeric (#60)
* The column 'flags' is not being labelled even if type = "label" (#61)

# eurostat 1.2.22

* The European Commission and the Eurostat generally uses ISO 3166-1 alpha-2 codes with two exceptions: EL (not GR) is used to represent Greece, and UK (not GB) is used to represent the United Kingdom. This now  can be handled with `harmonize_country_code()` which converts the raw data values from EL to GR and from UK to GB.
* Harmonized roxygen documentation to better follow CRAN conventions
* Changed Windows encoding to UTF for input files 
* Improved memory usage

# eurostat 1.2.21

* The `get_eurostat()` can now get data also from the Eurostat JSON API via `get_eurostat_json()`. It also have a new argument `type` to select labels for variable values instead of codes.
* Fix an error after update to `tidyr 0.4.0` (#47).

# eurostat 1.2.13

* New `select_time` argument for `get_eurostat()` to select a time frequency  in case of multi-frequency datasets. Now the `get_eurostat()` also gives an error if you try to get multi-frequency with other time formats than `time_format = "raw"`. (#30) `time` column is also now in ascending order.
* `get_eurostat()` gets a new argument `compress_file` to control compression of the cache file. Also cache filenames includes now all relevant arguments. (#28)
* For `search_eurostat()` a new type option `type = "all"` to search all types.
* For `label_eurostat()` new arguments. A `code` to retain also codes for spesified colums. A `eu_order` to order factor levels in Eurostat order, which uses the new function `dic_order()`. 
* Now `label_eurostat_vars(x)` gives labels for names, if x is other than a character or a factor and `label_eurostat_tables(x)` does not accept other than a character or a factor.
* For `get_eurostat()` a new argument `stringsAsFactors` to control the factor conversion of variables.
* `eurotime2date` (and `get_eurostat`) convers now also daily data. 

# eurostat 1.0.16

* Fixed vignette error

# eurostat 1.0.14 (2015-03-19)

* Package largely rewritten
* Vignette added
* Changed the value column to values in the get_eurostat output

# eurostat 0.9.1 (2014-04-24)

* Package collected from statfi and smarterpoland
