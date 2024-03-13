# Currency Converter Web API

This project is a simple ASP.NET Core Web API for currency conversion. It provides an endpoint to convert a specified amount from a source currency to a target currency.

## Installation

To run the project locally, make sure you have [.NET Core SDK](https://dotnet.microsoft.com/download) installed on your machine.

## Usage

1. Copy the solution package and place it in an appropriate folder path.

2. Check if the startup project is set to CurrencyConverterAPI, if not please do the same.

3. Run the project (ctrl + F5 )
	The API will start running locally at `https://localhost:7059`.

The API exposes the following endpoint:

### Parameters
- `sourceCurrency` (string): The ISO 4217 code of the source currency.
- `targetCurrency` (string): The ISO 4217 code of the target currency.
- `amount` (decimal): The amount to convert from the source currency.

### Response

The endpoint returns a JSON object with the following properties:

- `exchangeRate` (decimal): The exchange rate used for conversion.
- `convertedAmount` (decimal): The resulting amount in the target currency.

## Exchange Rates

The API supports conversions between the following currency pairs: USD, INR, EUR. Exchange rates are loaded from a local file called `exchangeRates.json`. You can override these exchange rates using environment variables.
Here, First User Environment Variable is given preference than System Environment variable will be looked for. 

## Testing
The project includes unit tests for the conversion logic, logging, and error handling. You can run the tests by locating to the tab Test -> Run All Tests:

## Project Edge cases Covered:

1. ExchangeRates json file not found exception handled.
2. Default Response || If the URL is invoked without query params then Default Error Message and ExchangeRates are displayed. 
3. Invalid input amount - negative request handled.
4. Invalid Currencies pair request handled.
5. User Environment variable as well as System Environment variable handled.
6. Dynamic value change in Json file and Environment variable has been handled. 
