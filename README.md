# Congress Stock Picks

This repo allow's you to pull data published by members of congress as part of the [STOCK Act](https://en.wikipedia.org/wiki/STOCK_Act). It will create a dataframe like the one below:

| Sale or Purchase | Ticker | Asset Type | Amount |Date |
| -- | -- | -- | -- | -- |
|S | RBLX | call | 100 | 01/20/2023 |
|P |AAPL |stock | 10000 | 03/17/2023 |

It relies on regexes and string parsing, so don't be surprised if it breaks in the future or doesn't work for every document 🤷‍♂️

--- 

The main steps are as follows:
1. Request the data from the [STOCK Act website](https://disclosures-clerk.house.gov/FinancialDisclosure) for a specific year
1. Get the list of filing listed as "P" - which belongs to stock purchases and sales
1. For the filings we're interested in, get pdf by matching the URL `https://disclosures-clerk.house.gov/public_disc/ptr-pdfs/{YEAR}/{DOCUMENT_ID}.pdf`
1. Use dubious regex to get the information from the pdf text 

## Usage

Run the Jupyter notebook

## Known limitations

- Getting stock purchase/sale price
- Getting option information (strike, expiration date)

Feel free to contribute these features
