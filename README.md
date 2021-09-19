# Web Scraping with Python

## Objective

This tutorial aims to show how to use the Python programming language to web scrape a website. Specifically, we will use the `requests` and `Beautiful Soup` libraries to scrape and parse data from [companiesmarketcap.com](https://companiesmarketcap.com/) and retrieve the “*Largest Companies by Market Cap*”.

We will learn how to scale the web scraping process by first retrieving the first company/row of the table, all companies of the website’s first page, and finally all 5301 companies from multiple pages. Finally, we will use `matplotlib` to visualise the most important information from the scraped dataset.

## Motivation

Web scraping is a technique employed to extract large amounts of data from the Web using intelligent automation. Web scraping is nowadays an essential tool for data scientists as it can be used to potentially retrieve/source hundreds, millions, or even billions of data points from the Internet’s seemingly endless frontier.
