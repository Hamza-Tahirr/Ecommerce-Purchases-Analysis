# Ecommerce Purchases Analysis

Exploratory data analysis of 10,000 e-commerce purchase records using pandas. The notebook works through 15 questions about the data, from basic structure checks to filtering, string handling and simple aggregations.

## Questions covered

1. Display the top 10 rows of the dataset
2. Display the last 10 rows of the dataset
3. Check the data type of each column
4. Check for null values
5. How many rows and columns are in the dataset?
6. Highest and lowest purchase prices
7. Average purchase price
8. How many people have French (`fr`) as their language?
9. How many job titles contain "engineer"?
10. Find the email of the person with the IP address `132.207.160.22`
11. How many people use Mastercard and made a purchase above 50?
12. Find the email of the person with the credit card number `4664825258997302`
13. How many purchases were made in the AM and how many in the PM?
14. How many people have a credit card that expires in 2020?
15. What are the top 5 most popular email providers?

## Dataset

The file `Ecommerce Purchases` (a CSV file without an extension) has 10,000 rows and 14 columns:

`Address`, `Lot`, `AM or PM`, `Browser Info`, `Company`, `Credit Card`, `CC Exp Date`, `CC Security Code`, `CC Provider`, `Email`, `Job`, `IP Address`, `Language`, `Purchase Price`

The records are fictional. The addresses, emails and card numbers are made up and are not real customer data.

## Method

Everything is done with pandas in a single notebook:

- `head`, `tail`, `dtypes`, `info` and `isna().sum()` to inspect the data
- `max`, `min` and `mean` on the purchase price
- Boolean filtering, including combined conditions with `&`
- `str.contains` with `case=False` to match job titles
- String splitting and slicing, in plain loops and with `apply` and lambdas, to pull the year out of `CC Exp Date` and the domain out of `Email`
- `value_counts` for the AM/PM split and the email provider ranking

Some questions are solved in two ways. For example, the 2020 card expiries are counted with a plain loop and then again with `apply`.

## Key findings

| Question | Result |
| --- | --- |
| Rows / columns | 10,000 / 14 |
| Missing values | None in any column |
| Highest / lowest purchase price | 99.99 / 0.00 |
| Average purchase price | about 50.35 |
| Language is French (`fr`) | 1,097 people |
| Job title contains "engineer" | 984 people |
| Mastercard and purchase above 50 | 405 people |
| AM / PM purchases | 4,932 / 5,068 |
| Card expires in 2020 | 988 people |
| Top email providers | hotmail.com (1,638), yahoo.com (1,616), gmail.com (1,605), smith.com (42), williams.com (37) |

## Tech stack

- Python 3
- pandas
- Jupyter Notebook

## Project structure

```
Ecommerce-Purchases-Analysis/
├── Ecommerce Purchases        # dataset (CSV)
├── Ecommerce Purchases.ipynb  # analysis notebook
├── requirements.txt
├── LICENSE
└── README.md
```

## Running the notebook

```bash
git clone https://github.com/Hamza-Tahirr/Ecommerce-Purchases-Analysis.git
cd Ecommerce-Purchases-Analysis

python -m venv venv
source venv/bin/activate        # on Windows: venv\Scripts\activate
pip install -r requirements.txt

jupyter notebook "Ecommerce Purchases.ipynb"
```

The notebook loads the dataset with a relative path, so start Jupyter from the repository folder.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
