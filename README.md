# Bubstal-test

eCommerce Scraper & Profit Analytics
Overview
An AI-powered eCommerce analysis tool for the Technical Coding Test, built in Google Colab. It enables users to select a Procurement Platform (1688, Shopee Taiwan) and Sales Platform (Rakuten Japan, Shopee Taiwan), mock scrape Top 10 products, match them across platforms, calculate profits, and visualize ROI using ipywidgets, requests, BeautifulSoup, SentenceTransformers, and matplotlib.
System Architecture
Modular system with clear data flow:

UI Module: ipywidgets dropdowns for platform/criteria selection.
Scraper Module: Mock scrapes product data due to Colab limitations.
Matcher Module: Uses SentenceTransformers for NLP-based product matching.
Profit Calculator Module: Computes profit and gross margin with mock exchange rates.
Output Module: Displays results in a DataFrame, plots ROI with matplotlib, and exports to CSV/Excel.

Data Flow: User selects options → Scraper fetches mock data → Matcher pairs products → Profit Calculator computes metrics → Output displays/exports results.
Setup Instructions
Run in Google Colab:

Open Google Colab and create a notebook.
Copy code from .ipynb into cells.
Install dependencies:!pip install requests beautifulsoup4 pandas numpy sentence-transformers ipywidgets matplotlib openpyxl reportlab


Enable ipywidgets:from google.colab import output
output.enable_custom_widget_manager()


Run UI cell to show dropdowns and "Start Analysis" button.
Select options and click "Start Analysis".
Run analysis cell to display results and plot.
Download analysis_results.csv/analysis_results.xlsx from Colab’s file panel.
Save notebook: File > Save a copy in Drive or File > Download > Download .ipynb.

Module Explanations

UI (create_ui): ipywidgets for interactive input.
Scraper (scrape_sales_platform, scrape_procurement_platform): Mock scrapes product details (name, price, sales, etc.) using requests and BeautifulSoup.
Matcher (match_products): Matches products with SentenceTransformers (similarity > 0.7).
Profit Calculator (calculate_profit, get_exchange_rate): Calculates profit/gross margin with mock shipping (10 units), fees (10%), and exchange rates.
Output (display_results, export_to_excel): Shows DataFrame, matplotlib ROI plot, and exports to CSV/Excel.

Limitations

Scraping: Mocked due to Colab’s lack of browser automation. Use Playwright/Selenium for real scraping.
UI: ipywidgets is basic compared to Streamlit.
Docker: Not supported in Colab.
Real Scraping: Needs DOM selectors and anti-bot handling.
