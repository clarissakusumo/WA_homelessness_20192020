# Readme (Documentation)

This repository contains a readme file along with two different datasets, the raw and normalized dataset for 2019-2020 individual homeless counts per county in Washington. The datasets are available to view in two different formats, CSV and XLXS). The dataset contains information about the counts of individual homeless in 2019 and 2020, in each county, which was obtained from the WA Department of Commerce website. The problem that the data are meant to address is that there has been an increase of homeless counts from 2019 (pre-COVID) to 2020 (during COVID) and there’s no easy access to the data points regarding the counts of homeless for each county, compared to the land area of the county and the population number of the county. The method of counting the individual homeless is called Point-in-Time (PIT), and all the counties use the same method to obtain the homeless counts.

## Contact
Clarissa Kusumo (ckusumo@uw.edu)

## Metadata
Metadata Schema: Project Open Data

| **Attribute** | **Value** |
| --- | --- |
| title | Individual Homeless Counts in Washington |
| description | This dataset consists of the Point-in-Time (PIT) counts of Individual homeless in Washington State, per County, in 2019 and 2020. The intended audience for this dataset is policymakers |
| describedBy | https://github.com/clarissakusumo/WA_homelessness_20192020/blob/main/README.md |
| keywords | “Homeless” “homelessness” “PIT” “Washington” “WA” WA Homelessness” “Homeless Counts” “PIT Counts”  |
| modified | March 3, 2022 |
| publisher | Clarissa Kusumo |
| contactPoint | Clarissa Kusumo , [Mailto:ckusumo@uw.edu](Mailto:ckusumo@uw.edu) |
| accessLevel | public |
| issued | March 3, 2022|
| language | English - US |
| landingPage | https://github.com/clarissakusumo/WA_homelessness_20192020 |
| references | [https://deptofcommerce.app.box.com/s/ek9pu2w07oz8d77gq6c1rlpxuwcw0515](https://deptofcommerce.app.box.com/s/ek9pu2w07oz8d77gq6c1rlpxuwcw0515) (for PIT individual Homeless Counts 2019-2020), [https://ce.naco.org/?find=true](https://ce.naco.org/?find=true) (for each county land area data), [https://www.census.gov/data/datasets/time-series/demo/popest/2010s-counties-total.html](https://www.census.gov/data/datasets/time-series/demo/popest/2010s-counties-total.html) (for each county population counts in 2019), [https://www.census.gov/library/stories/state-by-state/washington-population-change-between-census-decade.html](https://www.census.gov/library/stories/state-by-state/washington-population-change-between-census-decade.html) (for each county population counts in 2020) |
| accessURL | https://github.com/clarissakusumo/WA_homelessness_20192020/blob/main/WA_20192020_RawData.xlsx |
| downloadURL | https://github.com/clarissakusumo/WA_homelessness_20192020/blob/main/WA_20192020_RawData.xlsx |
| format | XLSX |
| mediaType | XLSX |

## Data Normalization

Since the dataset consists of a lot of ambiguous data, for instance, “<10”, I normalized the value to be “0” (in the NormalizedData dataset). Thus, when I performed the calculation for the percentages of homeless per population county, and also homeless counts per area, the value is not NULL. There are two sets of datasets, the first is the raw data (CSV and XLSX format), and the second is the normalized data (CSV and XLSX format). I performed normalization by first, taking the average of the raw data (for each variable), and then second, taking the standard deviation of the raw data (for each variable). After that, I calculated the Z-Score by taking the values of the variable minus the average value of the whole variable and dividing this result by the standard deviation of the whole variable. As can be seen from the normalized data, all of the values of the variables are on the same scale, meaning that each data point will be easier to be compared to each other. 

## File Naming Convention

The file naming convention should follow the format below:

	      State_Year_DatasetType

  Where _State_ is the State abbreviation of the dataset being reported (example: WA),
  
  _Year_ is the 4-digits year of the data being reported (example: 20192020) ,
  
  _DatasetType_ is the indication whether the dataset is raw data (“RawData”) or normalized data (“NormalizedData”)

## Data Dictionary

- Raw Data

| **Variable** | **Variable Label** | **Variable Type** | **Measurement Unit** | **Allowed Values** | **Description** |
| --- | --- | --- | --- | --- | --- |
| County Name | County | String | N/A | WA County Names | County in Washington State| 
| 2019 Homeless Counts | 2019_homeless | Numerical | N/A | Integer(positive numbers) | Total PIT Homeless Counts (Sheltered and Unsheltered) in 2019, obtained from Washington State Department of Commerce Website |
| 2019 Population Counts | 2019_pop | Numerical | N/A | Integer(positive numbers) | Total Population Counts in 2019, obtained from Census Data |
| 2020 Homeless Counts | 2020_homeless | Numerical | N/A | Integer(positive numbers) | Total PIT Homeless Counts (Sheltered and Unsheltered) in 2020, obtained from Washington State Department of Commerce Website |
| 2020 Population Counts | 2020_pop | Numerical | N/A | Integer(positive numbers) | Total Population Counts in 2020, obtained from Census Data |
| 2019 Percentage of Homeless in WA | 2019_percenthomelessstate | Numerical | Percentage(%) | Integer/Float | Percentage of Homeless Counts in 2019, obtained by dividing the total homeless counts for each county, with the Total Counts of Homeless Counts in Washington |
| 2020 Percentage of Homeless in WA | 2020_percenthomelessstate | Numerical | Percentage(%) | Integer/Float | Percentage of Homeless Counts in 2020, obtained by dividing the total homeless counts for each county, with the Total Counts of Homeless Counts in Washington |
| 2019 Percentage of Homeless per Population | 2019_percenthomelesspop | Numerical | Percentage(%) | Integer/Float | Percentage of Homeless Counts in 2019, obtained by dividing the total homeless counts for each county, with the Total Population Count of each County |
| 2020 Percentage of Homeless per Population | 2020_percenthomelesspop | Numerical | Percentage(%) | Integer/Float | Percentage of Homeless Counts in 2020, obtained by dividing the total homeless counts for each county, with the Total Population Count of each County |
| Area of Land | land_area | Numerical | Sq miles | Integer(positive numbers) | Area of Land of each County, obtained from National Association of Counties Website |
| 2019 Homeless Counts per area of land | 2019_homelessarea | Numerical | N/A | Integer(positive numbers | Count of Homeless per Area of Land per county in 2019, obtained by dividing the homeless counts per county with the area of land per county |
| 2020 Homeless Counts per area of land | 2020_homelessarea | Numerical | N/A | Integer(positive numbers | Count of Homeless per Area of Land per county in 2020, obtained by dividing the homeless counts per county with the area of land per county |

- Normalized Data

| **Variable** | **Variable Label** | **Variable Type** | **Measurement Unit** | **Allowed Values** | **Description** |
| --- | --- | --- | --- | --- | --- |
| County Name | County | String | N/A | WA County Names | County in Washington State| 
| Z-Score of 2019 Homeless Counts | z2019_homeless | Numerical | N/A | Float(positive or negative) | Z-Score of Total PIT Homeless Counts (Sheltered and Unsheltered) in 2019, obtained from Washington State Department of Commerce Website |
| Z-Score of 2019 Population Counts | z2019_pop | Numerical | N/A | Float(positive or negative) | Z-Score of Total Population Counts in 2019, obtained from Census Data |
| Z-Score of 2020 Homeless Counts | z2020_homeless | Numerical | N/A | Float(positive or negative) | Z-Score of Total PIT Homeless Counts (Sheltered and Unsheltered) in 2020, obtained from Washington State Department of Commerce Website |
| Z-Score of 2020 Population Counts | z2020_pop | Numerical | N/A | Float(positive or negative) | Z-Score of Total Population Counts in 2020, obtained from Census Data |
| Z-Score of 2019 Percentage of Homeless in WA | z2019_percenthomelessstate | Numerical | N/A | Float(positive or negative) | Z-Score of Percentage of Homeless Counts in 2019, obtained by dividing the total homeless counts for each county, with the Total Counts of Homeless Counts in Washington |
| Z-Score of 2020 Percentage of Homeless in WA | z2020_percenthomelessstate | Numerical | N/A | Float(positive or negative) | Z-Score of Percentage of Homeless Counts in 2020, obtained by dividing the total homeless counts for each county, with the Total Counts of Homeless Counts in Washington |
| Z-Score of 2019 Percentage of Homeless per Population | z2019_percenthomelesspop | Numerical | N/A | Float(positive or negative)| Z-Score of Percentage of Homeless Counts in 2019, obtained by dividing the total homeless counts for each county, with the Total Population Count of each County |
| Z-Score of 2020 Percentage of Homeless per Population | z2020_percenthomelesspop | Numerical | N/A | Float(positive or negative) | Z-Score of Percentage of Homeless Counts in 2020, obtained by dividing the total homeless counts for each county, with the Total Population Count of each County |
| Z-Score of Area of Land | zland_area | Numerical | N/A | Integer(positive numbers) | Z-Score of Area of Land of each County, obtained from National Association of Counties Website |
| Z-Score of 2019 Homeless Counts per area of land | z2019_homelessarea | Numerical | N/A | Float(positive or negative) | Z-Score of Count of Homeless per Area of Land per county in 2019, obtained by dividing the homeless counts per county with the area of land per county |
| Z-Score of 2020 Homeless Counts per area of land | z2020_homelessarea | Numerical | N/A | Float(positive or negative)| Z-Score of Count of Homeless per Area of Land per county in 2020, obtained by dividing the homeless counts per county with the area of land per county |
