# CSV File Format Standard Quick Guide
This page provides a quick guide to data stored using the CSV File Format. For a more detailed guide, see the full documentation of the standard available [here](csv_format_standard_documentation_20200818.md). An example of a dataset that adheres to the standard is available [here](csv_format_standard_demonstration_20200825.xlsx).

## Elements of the Standard
1. [Character Set](#1-character-set)
2. [File Name](#2.-file-name)
3. [Delimiter](#3-delimiter)
4. [Data Matrix](#4-data-matrix)
5. [Variable Name](#5-variable-name)
6. [Units](#6-units)
7. [Consistent Values](#7-consistent-values)
8. [Missing Data Values](#8-missing-data-values)
9. [Flags](#9-flags)
10. [Temporal Data](#10-temporal-data)
11. [Timestamp](#11-timestamp)
12. [Spatial Data](#12-spatial-data)

### 1. Character Set
|Proposed Element|*Required*|
|:---|:---|
|**Statement**|Use the standard US-ASCII character set without extensions.|
|**Format**||
|**Description**|Data stored using the comma separated values format (CSV) ([RFC 4180](https://tools.ietf.org/html/rfc4180)) must use the standard seven-bit American Standard Code for Information Interchange (US-ASCII) characters ([RFC 20](https://tools.ietf.org/html/rfc20)).|
|**Examples**|<code>! " # $ % & ' ( ) * + ' - . / 0-9 : ; < = > ? @ A-Z a-z { \| } ~</code>|

### 2. File Name
|Proposed Element|*Required*|
|:---|:---|
|**Statement**|Use unique, descriptive file names that follow the file naming conventions.|
|**Format**||
|**Description**|Unique file names that contains no spaces. Only letters, numbers, a hyphen "-" (ASCII Code 45), and an underscore "_" (ASCII Code 95) can be used in file names.|
|**Examples**|<code>NGEEArctic_BEO_VegetationPlot_A1E_2017.csv</code><br/><code>ngeearctic_beo_vegetation-plot-a1e_2017.csv</code>|

### 3. Delimiter
|Proposed Element|*Required*|
|:---|:---|
|**Statement**|Use a comma as the delimiter, and avoid commas except as a delimiter.|
|**Format**||
|**Description**|The delimiter between columns must be the comma character "," (ASCII Code 44). If a comma is needed within a cell (i.e., the comma is not meant as a delimiter), use a vertical bar "\|" (ASCII Code 124) instead of a comma. Alternatively, commas that are not meant to be delimiters must be protected by matching quotation marks (“ or ‘) around the entire value.|
|**Examples**|<code>variable_1,variable_2,variable_3,</code><br/><code>Doe\|Jane,Simpson\|Bart,Smith\|John,</code><br/><code>"Knoxville, TN","Bishop, CA","Savannah, GA",</code>|

### 4. Data Matrix
|Proposed Element|*Required*|
|:---|:---|
|**Statement**|File organized as a matrix of rows and columns with no empty lines and equal number of columns.|
|**Format**||
|**Description**|The contents of the file must be organized in a logical and readable matrix format. There can be no empty lines or rows in the file, and the file must contain the same number of columns across all of its rows.|
|**Examples**|<code></code>|

### 5. Variable Name
|Proposed Element|*Required*|
|:---|:---|
|**Statement**|Use unique, descriptive variable names.                                                                      |
|**Format**|text|
|**Description**|Unique variable names must be used. No spaces. Letters, numbers, a hyphen "-" (ASCII Code 45), and an underscore "_" (ASCII Code 95) are preferred in variable names.|
|**Examples**|<code>soil_temp_5cm,soil_temp_20cm,veg_abundance,veg_species</code>|

### 6. Units
|Proposed Element|*Recommended*|
|:---|:---|
|**Statement**|Provide approved variable units of measurement with the variable name.|
|**Format**||
|**Description**|Provide the units of measurement for the variable in the variable name following the same naming conventions for the variable. If units are not provided here, it must be documented elsewhere. Data should be represented with units of measurement approved by the International System of Units ([SP 330](https://www.nist.gov/pml/special-publication-330)), derived units (e.g., degree Celsius), or non-SI units accepted for use with SI (e.g., minute, hour, day, mixing ratio). Explanations of units the do not conform to the international standards must be documented elsewhere.|
|**Examples**|<code>soil_temp_c,total_depth_cm,bulk_density_g_cm-3</code>|

### 7. Consistent Values
|Proposed Element|*Required*|
|:---|:---|
|**Statement**|Variable units, type, and precision consistent within columns.|
|**Format**||
|**Description**|All data within a column must use the same units of measurement. Text and numeric data must not be used in the same column. Precision refers to the number of decimal places used for a variable.|
|**Examples**|<code></code>|

### 8. Missing Data
|Proposed Element|*Required*|
|:---|:---|
|**Statement**|Use a consistent missing data value.|
|**Format**|-9999 for numbers, NA for text|
|**Description**|If a cell does not contain a value, a missing data value must be indicated. Missing data must be represented by values that can never be construed as actual data and must be consistent across variables. For columns containing numeric data, "-9999" is preferred as the missing data value or use the correct precision given the data in the column. For columns containing character data, the string "NA" is preferred as the missing data value. Explanations for individual missing values can be reported as a separate variable (i.e., in an adjacent column). If a coding system is used to describe the missing data value, it must be documented elsewhere.|
|**Examples**|<code>-9999</code></br><code>NA</code>|

### 9. Flags
|Proposed Element|*Recommended if applicable*|
|:---|:---|
|**Statement**|Provide variable measurement uncertainty, limits of detection, data quality indicators, and other flags.|
|**Format**|number or text|
|**Description**|Measurement uncertainty, limits of detection, data quality indicators, and other flags pertaining to individual values should be reported as a separate variable (i.e., in an adjacent column) but only in addition to the reported values. If a coding system is used to describe the flags, it must be documented elsewhere.|
|**Examples**|<code>-8888</code></br><code>lower limit of detection</code>|

### 10. Temporal Data
|Proposed Element|*Required if applicable*|
|:---|:---|
|**Statement**|Provide temporal data in UTC format.|
|**Format**|YYYY-MM-DD hh:mm:ss|
|**Description**|All dates and times must be reported in Coordinated Universal Time (UTC) and follow the ISO 8601 standard ([RFC 3339](https://tools.ietf.org/html/rfc4180)). Note that the use of "Z" and "T" characters are unnecessary. All times must be preceded with a date. In cases where the entire file consists of temporal data collected at a single date and time, the date and time must be documented elsewhere if not provided as a variable. Temporal data using different standards can be provided as a separate variable (i.e., in an adjacent column) but only in addition to UTC format.|
|**Examples**|<code>2013-08-02 17:44:11</code>|

### 11. Timestamp
|Proposed Element|*Recommended if applicable*|
|:---|:---|
|**Statement**|Specify timestamps as the start, stop, midpoint, or average of measurement period.|
|**Format**|text|
|**Description**|For data with multiple timestamped records or when applicable, the variable name should specify if the measurement is the start, stop, or midpoint value, or it must be documented elsewhere.|
|**Examples**|<code>start_time,end_time</code>|

### 12. Spatial Data
|Proposed Element|*Required if applicable*|
|:---|:---|
|**Statement**|Provide spatial data in WGS84 decimal format.|
|**Format**|decimal degrees|
|**Description**|All geographic coordinates must be provided in WGS84 decimal format ([EPSG 4326](https://epsg.io/4326)). Latitude and longitude must be provided as separate variables (i.e., in an adjacent column). For geolocated records, each row must contain coordinates. In cases where the entire file consists of measurements collected at a single location, a pair of geographic coordinates must be documented elsewhere if not provided as variables. Spatial data using different standards can be provided as a separate variable (i.e., in an adjacent column) but only in addition to WGS84 decimal format.|
|**Examples**|<code>35.662045,-83.285439</code>|
