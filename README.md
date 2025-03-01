# ATCvet index


The Anatomical Therapeutic Chemical (ATC) index for veterinary medicinal
products ([ATCvet](https://atcddd.fhi.no/atcvet/atcvet_index/)) is a
system for the classification of substances intended for therapeutic use
in veterinary medicine.

Created using [ATCtools](https://github.com/amr-pub/ATC-tools).

## Combine .CSVs

``` r
library(here)
library(readr)
library(stringr)

# Get a list of file paths for files in the directory.
filepaths <- list.files(here::here(), full.names = TRUE)

# Get a list of file paths for .CSVs with one to two character names.
filepaths <- filepaths[stringr::str_detect(filepaths, "/[A-Za-z0-9]{1,2}.csv")]

# Read the .CSVs. 
ATCvet    <- readr::read_csv(file = filepaths)

# Write the ATCvet CSV.
readr::write_csv(ATCvet, here::here("ATCvet.csv"))
```
