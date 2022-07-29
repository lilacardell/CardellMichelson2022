# CardellMichelson2022

This is the GitHub repository for the paper "Price risk and small farmer maize storage in Sub-Saharan Africa: new insights into a long-standing puzzle" by Lila Cardell and Hope Michelson

Please contact Lila Cardell at lilac2 at illinois dot edu for questions on using the data and code in this respository

## Overview
The R code in this replication package imports and analysis publically available data on market prices, agricultural seasons, national crop production, geographic locations, and CPI. 
Two files run the code to import, aggregate, and analyze the data as well as generate the tables and graphs.

## Data Availability and Provenance Statements
There are multiple sources of publically available data  used in this paper:

1. Monthly maize prices are downloaded directly within the file "dataimport_042722" from the [HDX Global Data Exchange](https://data.humdata.org/dataset/global-wfp-food-prices) using an R package (rhdx). The data are collected and aggregated by the World Food Programme (WFP). The data are in the public domain.
Any issues should be directly to the package developer. In section 2, there is a line to download the set of maize prices "maizeprices_042722" from the "Clean Data" folder directly to avoid using this package. Note that if the database is updated retroactively, the dataset accessed as of April 2022 may differ from the updated database.

2. CPI data was dowloaded from the [International Financial Statistics Database](https://data.imf.org/?sk=4c514d48-b6ba-49ed-8ab9-52b0c1a0179b), and [FAOSTAT](https://www.fao.org/faostat/en/#data/CP) as of April 2022. The data are in the public domain and are available in the "Raw Data" folder.

3. Agricultural Season data was collected by FAO GIEWS and downloaded from the [University of Wisconsin](https://sage.nelson.wisc.edu/data-and-models/datasets/crop-calendar-dataset). The data are in the public domain and are available in the "Raw Data" folder. 

4. Market location data was found using the R geocode command from [TidyGeocoder](https://jessecambon.github.io/tidygeocoder). For any missing coordinates, there are two additional excel files with coordinate data from GoogleEarth.

5. National yield and production data were downloaded from [FAOSTAT](https://www.fao.org/faostat/en/*data/QCL) and [USDA Foreign Agricultural Service](https://apps.fas.usda.gov/psdonline/app/index.html#/app/downloads) as of April 2022. The data are in the public domain and are available in the "Raw Data" folder.


## Code
Code for data cleaning and analysis is provided as part of the replication package. It is available on [Github](https://github.com/lilacardell/CardellMichelson2022). 
The dataimport_042722 file imports the relevant data on market prices, agricultural seasons, national crop production, geographic location, and CPI. It aggregates the data and eliminates duplicates and errors, and then saves the relevant clean files to "CM2022.Rdata.
The dataanalysis_042722 file imports the "CM2022.Rdata" file from the "Clean Data" folder, analyzes it, and generates the tables and graphs in the paper.

## Approximate Run Time
The file dataimport_042722 will take approximately 30 minutes to run. The delay is due to the geocoding function.
The file dataanalysis_042722 will take 10-15 minutes to run, depending on how the ggplot functions are feeling.

## References
Sacks, W.J., D. Deryng, J.A. Foley, and N. Ramankutty (2010). Crop planting dates: an analysis of global patterns. Global Ecology and Biogeography 19, 607-620. DOI: 10.1111/j.1466-8238.2010.00551.x.
