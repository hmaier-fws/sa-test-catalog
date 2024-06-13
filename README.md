# sa-test-catalog
Source data for use in testing custom deployments of the Science Applications [Science Catalog](https://www.fws.gov/program/science-applications/science-catalog). The catalog landing page (https://www.fws.gov/science/catalog) the catalog content is rendered from data obtained from the catalog API (https://science-catalog.fws.gov/science/catalog)

## Other Science Catalog information

  - Display catalog sources: https://science-catalog.fws.gov/science/catalog/api/source
  - Display items (or item, if identifier is appended): https://science-catalog.fws.gov/science/catalog/api/item
  - Log (not sue of what?): https://science-catalog.fws.gov/science/catalog/api/log
  - QA/QC issues: https://science-catalog.fws.gov/science/catalog/api/item/qaqcissues
  - API documentation: https://science-catalog-test.djcase.com/science/catalog/server_doc/

# Source data for catalog testing

## `ak-catalog` directory

Source data for testing an Alaska instance of the catalog. The Alaska catalog is obtaining data from this directory and from ScienceBase records that have [Region 7 U.S. Fish and Wildlife Service Migratory Bird Management](https://www.sciencebase.gov/catalog/item/645bfee5d34ec179a83822eb) as a parent.

  - Source url: https://www.sciencebase.gov/catalog/item/645bfee5d34ec179a83822eb
  - Source url: https://hmaier-fws.github.io/sa-test-catalog/ak-catalog/
  - Test catalog: https://science-catalog-ak.djcase.com/science/catalog

## `test-waf` directory

One source of content for testing an initial version of the updated Science Applications catalog. Files placed in the `/test-waf` directory will be harvested by the testing instance of the science catalog.

  - Source URL: https://hmaier-fws.github.io/sa-test-catalog/test-waf/
  - Test catalog: https://science-catalog-test.djcase.com/science/catalog/

# Data Warehouse Testing
The following collections of files were complied for testing FWS Data Warehouse harvesting. Sample mdJSON data were downloaded from [ScienceBase](https://www.sciencebase.gov/catalog/item/4f4e476ee4b07f02db47e164) as mdJSON metadata.

  - mdJSON project metadata records only: [https://hmaier-fws.github.io/sa-test-catalog/sb-projects](https://hmaier-fws.github.io/sa-test-catalog/sb-projects)
  - A single project ([Gulf Coast LCD](https://www.sciencebase.gov/catalog/item/596d881de4b0d1f9f0616a89)) and all associated products: [https://hmaier-fws.github.io/sa-test-catalog/gulfcoast-proj](https://hmaier-fws.github.io/sa-test-catalog/gulfcoast-proj)