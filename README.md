# Jumia Flash Sales Scraper

A hybrid web scraper that extracts flash sale products from Jumia Kenya and saves them to a CSV file.

## Tech Stack

- **Selenium** — opens Chrome and loads the JavaScript-rendered page
- **BeautifulSoup4** — parses the HTML and extracts product data
- **Pandas** — saves the data to a CSV file
- **Webdriver Manager** — automatically manages the Chrome driver

## What it scrapes

| Field | Description |
|---|---|
| Brand | Product brand name |
| Product Name | Full product name |
| New Price | Current flash sale price |
| Old Price | Original price before discount |
| Discount | Percentage discount |

## Setup

### 1. Clone the repo
```bash
git clone <your-repo-url>
cd JumiaFlashSales_Scraper
```

### 2. Create and activate virtual environment
```bash
python -m venv env
source env/Scripts/activate
```

### 3. Install dependencies
```bash
pip install selenium webdriver-manager beautifulsoup4 pandas
```

### 4. Run the scraper
```bash
jupyter notebook jumia_scraper.ipynb
```

## Output

A `jumia_flash_sales.csv` file is generated in the project folder with all scraped products.

## How it works

1. Selenium opens a headless Chrome browser
2. Navigates to `https://www.jumia.co.ke/flash-sales/`
3. Loops through all pages until no products are found
4. BeautifulSoup parses each page and extracts product data
5. Pandas saves everything to CSV

## Notes

- Flash sales on Jumia are time-limited and rotate throughout the day
- The scraper stops automatically when it runs out of pages
- Headless mode runs Chrome invisibly in the background