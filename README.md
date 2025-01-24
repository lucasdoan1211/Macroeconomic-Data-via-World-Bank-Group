# Economic Indicators API - World Bank Data Extraction

This repository provides a Python script designed to retrieve and process macroeconomic indicators for any country listed in the World Bank's Data Bank. It leverages the World Bank API to gather detailed economic, social, and financial data, offering an efficient way to conduct analysis or build custom reports.

## Features
Flexible Country Selection: Specify any country's ISO 3166-1 alpha-3 code to retrieve data (e.g., PER for Peru).

Diverse Indicator Range: Access a predefined set of 23 economic indicators, including GDP growth, employment statistics, and financial metrics.

Customizable Time Range: Configure the script to filter data starting from a specific year (e.g., 2010).

Dynamic Data Filtering: Automatically excludes missing values to ensure clean datasets.

Export to CSV: Outputs a processed and pivoted dataset in CSV format for further analysis.

## Prerequisites
Ensure you have the following installed:

Python 3.7 or higher
Required libraries:
requests
pandas

Refer to the DataBank Economic Series Names to identify the corresponding code for the economic indicator you wish to retrieve. Each indicator in the World Bank DataBank is associated with a unique code, which must be specified in the script to fetch the desired data.

1. Base Configuration
The script uses the World Bank's API (https://api.worldbank.org/v2) as the base URL. You can specify:

Country Code: Use the ISO 3166-1 alpha-3 code (e.g., PER for Peru).
Indicator Codes: A list of World Bank indicator codes to retrieve data. Examples:
NY.GDP.MKTP.KD.ZG - GDP Growth Rate
SL.AGR.EMPL.ZS - Employment in Agriculture (%)
FR.INR.DPST - Deposit Interest Rates
Start Year: Specify the minimum year for data retrieval (e.g., 2010).


2. Data Retrieval
The script sends requests for each indicator, processes the response, and filters records:

Only includes entries with non-missing values.
Filters results by the specified start year.


3. Data Transformation
The collected data is transformed into a pivot table, where:

Rows: Indicators
Columns: Years
Values: Data values
4. Export
The resulting pivot table is exported as a CSV file to the specified location for analysis.

Example Usage
python
Copy
Edit
# Configuration
country_code = "PER"  # Specify country code (e.g., 'PER' for Peru)

start_year = 2010  # Define start year for filtering

output_path = "/path/to/output/Economic Indicators.csv"  # Output CSV path

# Run the script to retrieve and save data
Output Example

The generated CSV file will have the following structure:

Indicator	2010	2011	2012	...

GDP Growth (annual %)	8.4	6.5	5.8	...

Employment in Agriculture (%)	25.3	24.8	24.5	...

Deposit Interest Rates (%)	4.7	4.3	4.1	...

## Customization
Change Country

Update the country_code variable with the ISO code of your desired country.

## Add/Remove Indicators

Modify the indicator_codes list to include or exclude specific indicators.

Change Output File Path

Update the file path in the to_csv() method to save the output in a preferred location.

## Error Handling

The script logs failed API requests for indicators and their corresponding HTTP status codes.
Ensure the country code and indicator codes are valid per the World Bank Data API documentation.

## Contribution
Contributions, suggestions, and feature requests are welcome. Feel free to open an issue or submit a pull request.
