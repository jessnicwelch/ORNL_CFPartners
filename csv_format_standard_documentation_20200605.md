# Guidelines for Data Stored using the CSV File Format

The proposed CSV standard is derived from guidelines and recommendations defined by some popular Earth Science communities. The following details the guidelines and expectations for each data file that can responsibly be formatted as a flat file. Many of the standards correspond with fields included in the File-Level Metadata (FLMD) Guide. "Required' fields represent the ideal file for interoperable and machine-readable data. Descriptions with the phrase "must be documented elsewhere" references a yet-to-be-determined implementation of FLMD capture. These standards are a result of research and community feedback.

**1. Use the standard US-ASCII character set without extensions.** *REQUIRED*  
Data stored using the comma separated values format (CSV) ([RFC 4180](https://tools.ietf.org/html/rfc4180)) must use the American Standard Code for Information Interchange (US-ASCII) character-encoding scheme.

**2. No ASCII control characters except for end of line characters.** *REQUIRED*  
The file must use the standard seven-bit ASCII characters ([RFC 20](https://tools.ietf.org/html/rfc20)) and, must not contain control characters except for end-of-line characters: "HT" (Horizontal Tab), "LF" (Line Feed), and "CR" (Carriage Return).

![ASCII Table](asciitable.png)

*The characters numbered 0 to 31, inclusive, represent non-printing characters that are not directly displayed, but control how the data are interpreted. These characters were designed for when text was processed by teletype terminals, but some are still used by computer operating systems.*

**3. Use unique, descriptive file names that follow the file naming conventions.** *REQUIRED*  
Unique file names must be used. No spaces. Only letters, numbers, a hyphen "-" (ASCII Code 45), and an underscore "_" (ASCII Code 95) can be used in file names.

```
example_filename_2020-06-05.csv
```

**4. Use a comma as the delimiter.** *REQUIRED*  
The delimiter between columns must be the comma character "," (ASCII Code 44).

```
variable_1,variable_2,variable_3,
aaa,bbb,ccc
```

**5. Avoid commas except as a delimiter.** *REQUIRED*  
If a comma is needed within a cell (i.e., not meant as a delimiter), use a vertical bar "|" (ASCII Code 124) instead of a comma.

```
name_1,name_2,name_3,
Doe|Jane, Simpson|Bart, Smith|John,
```

Alternatively, commas that are not meant to be delimiters must be protected by matching quotation marks (“ or ‘) around the entire value.

```
name_1,name_2,name_3,
"Doe, Jane", "Simpson, Bart", "Smith, John",
```

**6. File organized as a matrix of rows and columns.** *REQUIRED*  
The contents of the file must be organized in a logical and readable matrix format.

| row 1 column 1 | row 1 column 2 | row 1 column 3 |
|---|---|---|
| row 2 column 1 | row 2 column 2 | row 2 column 3 |
| row 3 column 1 | row 3 column 2 | row 3 column 3 |
| row 4 column 1 | row 4 column 2 | row 4 column 3 |

**7. No empty lines or rows.** *REQUIRED*  
No empty lines or rows in the file.

**8. Each row must have the same number of columns.** *REQUIRED*  
The file must contain the same number of columns across all of its rows.

**9. Use unique, descriptive variable names that follow the variable naming conventions** *REQUIRED*  
Unique variable names must be used. No spaces. Only letters, numbers, a hyphen "-" (ASCII Code 45), and an underscore "_" (ASCII Code 95) can be used when providing variable units of measurement. Parenthesis "(" ")" (ASCII Code 40, 41) can be used when providing variable units of measurement following the variable name (e.g., total_depth(cm), bulk_density(g_cm-3)). Variables for FLMD extraction should follow a standardized variable naming convention.

```
mer
```

**10. Provide variable units of measurement** *REQUIRED*  
Provide the units of measurement for the variable in the variable name following the same naming conventions for the variable (e.g., total_depth(cm), bulk_density(g_cm-3)). If units are not provided here, it must be documented elsewhere. Data should be represented with units of measurement approved by the International System of Units (SI system), derived units (such as degree Celsius), or non-SI units accepted for use with SI (such as minute, hour, day, mixing ratio). Units of measurement and representations that do not conform to the international standards must be documented elsewhere.

```
mer
```

**11. Variable units, type, and precision consistent within columns** *REQUIRED*  
All data within a column must use the same units of measurement. Text and numeric data must not be used in the same column. Precision refers to the number of decimal places used for a variable.

```
mer
```

**12. Use a consistent missing data value** *REQUIRED*  
If a cell does not contain a value, a missing data value must be indicated. Missing data must be represented by values that can never be construed as actual data and must be consistent across variables. For columns containing numeric data, "-9999" is preferred as the missing data value or use the correct precision given the data in the column. For columns containing character data, the string "NA" is preferred as the missing data value. Explanations for individual missing values can be reported as a separate variable (column). If a coding system is used to describe the missing data value, it must be documented elsewhere.

```
mer
```

**13. Provide variable measurement uncertainty** *RECOMMENDED*  
Measurement uncertainty for individual values should be reported as a separate variable (column). If a coding system is used to describe measurement uncertainty, it must be documented elsewhere.

```
mer
```

**14. Provide variable measurement limits of detection** *RECOMMENDED*  
Limits of detection for individual values should be reported as a separate variable (column). If a coding system is used to describe limits of detection, it must be documented elsewhere.

```
mer
```

**15. Provide variable data quality flags** *RECOMMENDED*  
Quality flags for individual values should be reported as a separate variable (column). If a coding system is used to describe quality flags, it must be documented elsewhere.

```
mer
```

**16. Provide temporal data in UTC format** *REQUIRED*  
All dates and times must be reported in Coordinated Universal Time (UTC) and follow the ISO 8601 standard ([RFC 3339](https://tools.ietf.org/html/rfc4180)). All times must be preceded with a date. In cases where the entire file consists of temporal data collected at a single date and time, the date and time must be documented elsewhere. Temporal data using different standards can be provided as a separate variable (column) in addition to UTC format.

```
mer
```

**17. Specify timestamps as the start, stop, midpoint, or average of measurement period** *RECOMMENDED*  
For timestamped data, the variable name should specify if the measurement is the start, stop, or midpoint or it must be documented elsewhere.

```
mer
```

**18. Provide spatial data in WGS84 decimal format (EPSG:4326)** *REQUIRED*  
All geographic coordinates must be provided in WGS84 decimal format ([EPSG:4326](https://epsg.io/4326)). Latitude and longitude must be provided as separate variables. In cases where the entire file consists of measurements collected at a single location, a pair of geographic coordinates must be documented elsewhere. Spatial data using different standards can be provided as a separate variable (column) in addition to WGS84 decimal format.

```
mer
```
