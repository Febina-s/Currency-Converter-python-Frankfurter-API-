#  Currency Converter Using Python & Frankfurter API


A fully functional currency conversion tool built using **Python** and the **Frankfurter Exchange Rate API**. This project allows users to convert an amount from one currency to another by fetching **real-time** or **historical** exchange rates. It demonstrates how to handle APIs, parse JSON, manage user input, implement error-handling, and create an interactive Python console application.


---


##  About the Project


Currency conversion is widely used in finance, travel, international business, e-commerce, and data analytics. This project focuses on building a practical and reliable solution that fetches exchange rates directly from a trusted source — **Frankfurter API**, which uses data from the European Central Bank.


This project showcases:
- Real-world API integration
- Sending HTTP requests using Python
- Using query parameters effectively
- Parsing JSON responses
- Handling errors and invalid inputs
- Displaying results in a clean, user-friendly format


The program asks the user to input:
1. **Date** (example: `latest` or `yyyy-mm-dd`)
2. **Base currency** (the currency you have)
3. **Target currency** (the currency you want to convert to)
4. **Amount** to convert

 It then constructs the correct API URL, fetches exchange rate data, calculates the final converted amount, and displays the output clearly.


This is a great beginner-friendly project and a strong showcase for GitHub, especially for learners pursuing **data analysis**, **Python development**, or **API-based applications**.


---


##  Features


- Convert between any two currencies
- Supports **latest** or **historical** dates
- Uses real-time exchange rates from **Frankfurter API**
- Clean user interaction with clear instructions
- Detailed error handling
- Beginner-friendly and well-structured code


---


##  Technologies Used


- **Python 3**
- **Requests library**
- **Frankfurter Exchange Rate API**
- **JSON data parsing**

##  How It Works
- A date (`latest` or a specific date like `2024-09-10`)
- A base currency (e.g., USD)
- A target currency (e.g., INR)
- The amount to convert


2. The program constructs a URL such as:
```
https://api.frankfurter.app/latest?base=USD&symbols=INR
```


3. A GET request is sent to the API.


4. Data is received in JSON format.


5. The script extracts the exchange rate, calculates the converted amount, and displays the final result.


---


##  Code Snippet


```python
import requests


base_url = "https://api.frankfurter.app"


date = input("Enter date (yyyy-mm-dd) or type 'latest': ").strip().lower()
if date == "latest":
date = "latest"


base = input("Convert from (currency code, e.g., USD): ").upper()
curr = input("Convert to (currency code, e.g., INR): ").upper()
amt = float(input(f"How much {base} would you like to convert?: "))


url = f"{base_url}/{date}?base={base}&symbols={curr}"
response = requests.get(url)


if not response.ok:
print(f"\nError {response.status_code}:")
try:
print(response.json().get('error', "Unknown error"))
except:
print("Could not fetch error details.")
else:
data = response.json()
rate = data['rates'][curr]
result = amt * rate


print(f"\n{amt} {base} = {result} {curr} (Rate date: {data['date']})")
```


---


##  Example Output


```
Enter date (yyyy-mm-dd) or type 'latest': latest
Convert from (currency code, e.g., USD): USD
Convert to (currency code, e.g., INR): INR
How much USD would you like to convert?: 10


10 USD = 833.50 INR (Rate date: 2024-12-09)
```


---

# Supported Currencies

This file lists all the currencies currently supported in the project.

##  Supported Currency Codes

```
{'AUD': 'Australian Dollar',
 'BGN': 'Bulgarian Lev',
 'BRL': 'Brazilian Real',
 'CAD': 'Canadian Dollar',
 'CHF': 'Swiss Franc',
 'CNY': 'Chinese Renminbi Yuan',
 'CZK': 'Czech Koruna',
 'DKK': 'Danish Krone',
 'EUR': 'Euro',
 'GBP': 'British Pound',
 'HKD': 'Hong Kong Dollar',
 'HUF': 'Hungarian Forint',
 'IDR': 'Indonesian Rupiah',
 'ILS': 'Israeli New Sheqel',
 'INR': 'Indian Rupee',
 'ISK': 'Icelandic Króna',
 'JPY': 'Japanese Yen',
 'KRW': 'South Korean Won',
 'MXN': 'Mexican Peso',
 'MYR': 'Malaysian Ringgit',
 'NOK': 'Norwegian Krone',
 'NZD': 'New Zealand Dollar',
 'PHP': 'Philippine Peso',
 'PLN': 'Polish Złoty',
 'RON': 'Romanian Leu',
 'SEK': 'Swedish Krona',
 'SGD': 'Singapore Dollar',
 'THB': 'Thai Baht',
 'TRY': 'Turkish Lira',
 'USD': 'United States Dollar',
 'ZAR': 'South African Rand'}
```

##  Usage

You can use any of these currency codes as input in the converter.


## Key Takeaways / Skills Learned

* Understanding how to work with REST APIs using Python.
* Constructing API request URLs dynamically based on user input.
* Handling API responses and checking for errors using `response.ok`.
* Parsing JSON data returned by the API.
* Performing real‑time currency conversion using exchange rate data.
* Implementing basic input validation and clean user prompts.
* Getting familiar with Python modules like `requests`.
* Improving command‑line interaction skills by building a user‑friendly CLI tool.
* Structuring small Python projects for use in GitHub.
* Writing documentation (README.md) that explains functionality and usage.



---


##  Future Improvements


- Build a GUI using Tkinter or PyQt
- Create a web app using Streamlit
- Add dropdown lists for currencies
- Show historical charts using Matplotlib
- Convert multiple currencies at once


---

##  Author


**FEBINA S**


- LinkedIn: https://www.linkedin.com/in/febina-s-083436347/
- GitHub: https://github.com/Febina-s


---


Thank you for checking out the project! Feel free to contribute or suggest improvements.



