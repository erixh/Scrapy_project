# Web Crawler Project

A Python web scraping project built with Scrapy framework for extracting quotes and author information from quotes.toscrape.com.

## Features

- **Quotes Spider**: Scrapes quotes with text, author names, and supports tag-based filtering
- **Authors Spider**: Extracts detailed author information including names, birthdates, and biographies
- **Data Export**: Outputs scraped data in JSON Lines format
- **Pagination Support**: Automatically follows pagination links to scrape all available data

## Requirements

- Python >= 3.11
- Scrapy >= 2.13.1

## Installation

1. Clone the repository:
```bash
git clone https://github.com/erixh/Scrapy_project.git
cd Scrapy_project
```

2. Create and activate a virtual environment:
```bash
python -m venv .venv
# On Windows
.venv\Scripts\activate
# On macOS/Linux
source .venv/bin/activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
# or using uv
uv sync
```

## Usage

Navigate to the tutorial directory and run the spiders:

```bash
cd tutorial
```

### Running the Quotes Spider

```bash
# Scrape all quotes
python -m scrapy crawl quotes

# Scrape quotes with specific tag
python -m scrapy crawl quotes -a tag=inspirational

# Save output to file
python -m scrapy crawl quotes -o quotes.json
```

### Running the Authors Spider

```bash
# Scrape author information
python -m scrapy crawl author

# Save output to file
python -m scrapy crawl author -o authors.json
```

### Using Scrapy Shell for Testing

```bash
python -m scrapy shell "https://quotes.toscrape.com"
```

## Spiders

### QuotesSpider (`quotes`)
- **Target**: https://quotes.toscrape.com
- **Data Extracted**: Quote text, author names
- **Features**: 
  - Tag-based filtering (use `-a tag=tagname`)
  - Automatic pagination
  - Follows all quote pages

### AuthorSpider (`author`)
- **Target**: https://quotes.toscrape.com
- **Data Extracted**: Author names, birthdates, biographies
- **Features**:
  - Follows author detail pages
  - Extracts comprehensive author information
  - Automatic pagination

## Output

The scraped data is saved in JSON Lines format in the `content.jsonl` file, containing structured data for further analysis or processing.

## Development

To add new spiders or modify existing ones:

1. Create new spider files in `tutorial/tutorial/spiders/`
2. Define data structures in `items.py`
3. Configure data processing in `pipelines.py`
4. Adjust settings in `settings.py`


