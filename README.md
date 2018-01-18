
<!-- README.md is generated from README.Rmd. Please edit that file -->
OxShef: RMarkdown Template Site
===============================

This is a template repository for adding content to the OxShef collaboration between University of Oxford and University of Sheffield. Please use this template if your site matches these criteria:

-   The site will be written using RMarkdown files
-   The site will make use of R output

The OxShef collaboration covers many different technologies and it might not be appropriate to use RMarkdown in all cases, in which case please do consider adding a new template repository so others can create similar subsites in the future.

Current websites in OxShef that use this template include:

-   [OxShef Charts](https://oxshef.github.io/oxshef_charts/): A guide to different visualisation options for visualising research data

At the last full-build of the template the following R packages were required to build this package:

``` r
library("tidyverse")
list.files(pattern = "Rmd", recursive = TRUE) %>%
  map(., ~readLines(.x, warn = FALSE)) %>%
  paste(collapse = "") %>%
  str_extract_all("library\\([^()]+\\)") %>%
  str_extract_all("\\([^()]+\\)") %>%
  .[[1]] %>%
  gsub("[^[:alnum:].]", "", .) %>%
  unique()
#> [1] "highcharter" "tidyverse"   "gapminder"
```

Features of the site
====================

This template borrows heavily from the design of the [rmarkdown.rstudio.com](rmarkdown.rstudio.com) website, in order to use it effectively you must be aware of the following:

1.  Use the `_render-site.R` script to safely generate the website by knitting together all `.Rmd` files in the root directory of the project
2.  Modify `_site.yml` to change the globaly used CSS and which elements from `includes/` are automatically included in all pages
3.  `includes/` contains re-usable website elements as follows:
    -   `includes/include_header.html` defines the horizontal navigation displayed at the top of each page
    -   `includes/include_footer.html` defines the footer displayed at the bottom of each page
4.  Add new pages by duplicating the example-page.Rmd file

About OxShef
============

OxShef is a collaboration between the [University of Oxford](idn.it.ox.ac.uk) and [University of Sheffield](http://rse.shef.ac.uk/).

Copyright and License
=====================

The contents of this website, text and code, are made available under both a CC-BY and BSD license.

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.

Copyright 2017, University of Oxford and University of Sheffield
