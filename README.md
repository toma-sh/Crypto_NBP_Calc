# Crypto Purchase Cost Calculator

This web application is a basic tool designed to calculate the total purchase cost in Polish zloty (PLN) for cryptocurrencies bought with various currencies (USD, EUR, and PLN). It supports both file import (CSV or JSON) and manual entry of purchase data.

## Features

- **File Import:** Upload a CSV or JSON file containing:
  - **CSV format:** `date|amount|currency` (e.g., `2025-04-01|100.50|USD`)
  - **JSON format:** An array of objects with keys `date`, `amount`, and `currency`
- **Manual Entry:** Add purchase entries manually using a form that includes:
  - Date picker for the purchase date
  - Input field for the purchase amount
  - Dropdown to select the currency (default is USD)
- **Dynamic Exchange Rate Conversion:** For each entry, the application:
  - Fetches the historical exchange rate from the NBP API for USD and EUR on the specified purchase date
  - Uses a conversion rate of 1 for PLN
- **Calculation:** Converts each entry to PLN and computes the total cost.

## How It Works

1. **Data Input:** Users can either upload a file with the purchase data or add entries manually via the form.
2. **Data Processing:** The application parses the input file or manual entries and populates a table to display all records.
3. **API Fetch:** For each record in USD or EUR, the app fetches the corresponding historical exchange rate from the NBP API. For PLN, the rate is set as 1.
4. **Cost Calculation:** The application calculates the cost of each purchase in PLN and sums them to provide a total cost, which can be used for tax reporting purposes.

## Usage

### Prerequisites

- A modern web browser with JavaScript enabled.
- An active internet connection to access the NBP API for exchange rates.

### How to Run

1. **Open the Application:**  
   Open the `index.html` file in your browser.

2. **File Import:**  
   - Click the file input button to select a `.csv` or `.json` file formatted as described in the **Features** section.

3. **Manual Entry:**  
   - Use the date picker to select the purchase date.
   - Enter the amount of the purchase.
   - Select the currency from the dropdown (USD, EUR, or PLN).
   - Click the "Add Entry" button to add the record to the list.

4. **Calculation:**  
   - Once all entries are loaded or added, click the "Calculate Cost in PLN" button.
   - The application will fetch exchange rates as needed and display the total cost in PLN.

### API Endpoint Details

- **NBP API:**  
  - For USD: `https://api.nbp.pl/api/exchangerates/rates/A/USD/{date}/?format=json`
  - For EUR: `https://api.nbp.pl/api/exchangerates/rates/A/EUR/{date}/?format=json`
  - For PLN: The rate is always set to 1 (no API call required).

## File Structure

- **index.html:** Contains the HTML, CSS, and JavaScript that power the application.
- **README.md:** Provides an overview of the project, usage instructions, and other details.

## Future Improvements

- Enhanced input validation and error handling.
- Improved user interface for a better user experience.
- Extension to support more currencies and bulk data processing.
- Option to export results after calculation.

## License

This project is open source and available under the [MIT License](LICENSE).

## Acknowledgments

- [NBP API](https://www.nbp.pl/homen.aspx?f=/en/onLineWidok.html) for providing access to historical exchange rates.
