# CSV File format standard Quick Guide
This page provides a quick guide for the CSV standard. For a more detailed guide see our full documentation of the standard [here](csv_format_standard_documentation_20200818.md). For a downloadable CSV example that adheres to CSV standard click [here](csv_format_standard_demonstration_20200825.xlsx)

## Elements of the standard
1. [Character Set](#1.-Character-set-for-a-csv-file)
2. [File Name](#2.-file-name)

### 1. Character set for a csv file
|Character set format |<code>Required</code>                   |
|:------------------------------------|:---------------------------------------------------|
|**Statement**|Use the standard US-ASCII character set without extensions|
|**Category**|File|
|**Description**                     | Data stored using the comma separated values format (CSV) (RFC 4180) must use the standard seven-bit American Standard Code for Information Interchange (US-ASCII) characters (RFC 20). |
|**Examples**                         | LAB_ID, 80873, CL_mg/L|

### 2. File Name
|File name format |<code>Required</code>                   |
|:------------------------------------|:---------------------------------------------------|
|**Statement**|Use unique, descriptive file names that follow the file naming conventions.|
|**Category**|File|
|**Description**                     | Unique file names that contains no spaces. Only letters, numbers, a hyphen "-" (ASCII Code 45), and an underscore "_" (ASCII Code 95) can be used in file names. |
|**Examples**                         | SPRUCE_pore_water_chemistry_20191203|
