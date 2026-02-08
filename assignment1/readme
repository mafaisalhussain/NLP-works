# DATA 622 – Homework 1

**Web Scraping with Requests and BeautifulSoup**

## Overview

This assignment demonstrates basic web scraping using Python. The `requests` library was used to retrieve web pages and `BeautifulSoup` was used to parse HTML content and extract information.

## Tasks Completed

1. Attempted to retrieve [https://www.visitmaryland.org/](https://www.visitmaryland.org/) and obtained the HTTP status code.
2. Extracted visible text from the page.
3. Retrieved headings (h1, h2, h3) from the Wikipedia page for *Natural Language Processing*.
4. Extracted URLs (links) from the same Wikipedia page.
5. Extracted the first paragraph of the article and saved it to a text file (`nlp_intro.txt`).

## Important Observation

The Maryland tourism website returned **HTTP 403 (Forbidden)**.
The page is protected by Cloudflare and requires JavaScript and cookies.
Since Python `requests` does not execute JavaScript, the server returned a verification page instead of the actual website content.

The Wikipedia page worked correctly because it allows automated requests.

## Technologies Used

* Python
* requests
* BeautifulSoup (bs4)
* lxml parser
* Jupyter Notebook

## Output Files

* `nlp_intro.txt` – first paragraph from the NLP Wikipedia article
* Jupyter Notebook containing code and outputs

## Conclusion

This assignment showed that web scraping works well for static HTML pages but may fail on protected or JavaScript-based websites. Wikipedia is scrape-friendly, while some sites block automated requests.
