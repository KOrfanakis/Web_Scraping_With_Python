# Web Scraping with Python

<img src="/Images/01-Intro_Image.jpg" alt="drawing"/>

## Objective

The aim of this tutorial is to show how to use the Python programming language to web scrape a website. Specifically, we will use the `requests` and `Beautiful Soup` libraries to scrape and parse data from [companiesmarketcap.com](https://companiesmarketcap.com/) and retrieve the “*Largest Companies by Market Cap*”.

We will learn how to scale the web scraping process by first retrieving the first company/row of the table, all companies of the website’s first page, and finally all 5301 companies from multiple pages. Finally, we will use `matplotlib` to visualise the most important information from the scraped dataset.

## Motivation

Web scraping is a technique employed to extract large amounts of data from the Web using intelligent automation. Web scraping is nowadays an essential tool for data scientists as it can be used to potentially retrieve/source hundreds, millions, or even billions of data points from the Internet’s seemingly endless frontier.

## How Does It Work?

The first step in performing web scraping involves understanding what a webpage is. Simply put, a webpage is a text document provided by a website and displayed to a user in a web browser. Such documents are written in the [HTML language](https://html.com/).

HTML (which stands for HyperText Markup Language) is the most fundamental building block of the World Wide Web. It is the underlying source code of all webpages (along with CSS and JavaScript) as it encodes the displayed content and the overall structure of a webpage. HTML documents are files that end with a .html or .htm extension. We can easily access the HTML source code using the ‘view page source’ or ‘inspect’ tools of our browser.

Finally, a web scraper is a computer program that can understand an HTML document, parse it and extract useful information. To build a successful web scraper, we need at least to have a basic knowledge/understanding of HTML. If you are already familiar with HTML, you can skip the following section.

## HTML (Optional)

An HTML file is made of the so-called elements. An element represents semantics or meaning. Typically, an element includes an opening tag enclosed in angle brackets (\<tag>) and a closing tag enclosed in angle brackets but with a forward slash preceding the tag (\</tag>). The content of an HTML element is the information between its opening and closing tags.

```
<tag_name>Content</tag_name>
```

Elements in HTML can have attributes, i.e. values added to the opening tag to define additional characteristics or properties of the element. HTML attributes consist of a name and a value using the following syntax: name = "value".

```
<tag_name attribute_name="value">Content</tag_name>
```

Everything written in HTML is either an element or contained in an element (or both). In other words, HTML is organised into a family tree structure since HTML elements can have parents, grandparents, siblings, children, grandchildren, etc.

```
<body>
  <div>
    <h1>It's div's child and body's grandchild</h1>
    <h2>It's h1's sibling</h2>
  </div>
</body>
```
Note that the code is formatted such that the indentation level of text increases once for each level of nesting.

Every HTML file must have one grand/root element called \<html>. This element contains all other elements of the document. It is necessary that <html> always has two child elements:
  
- The \<head> element: a container for metadata, i.e. information about an HTML page that is not displayed on the webpage itself.
- The \<body> element: it represents the main content of an HTML document displayed on the browser.
  
```
<html>
  <head>
    <!-- META INFORMATION goes here -->  
  </head>
  <body>
    <!-- PAGE CONTENT goes here -->
  </body>
</html>
```  
  
For more information, please use the links in the References section of the notebook.

## Web Scraping Workflow

The workflow for web scraping with Python can be divided into the following three steps:
  
1. **Obtaining the HTML**: Firstly, we need to send an HTTP request to the webpage server that we want to scrape. If the request is successful, the server will respond with the HTML content of the page.
  
2. **Parsing the HTML**: Most of the obtained HTML data is nested, making it difficult to extract information using stand string processing techniques. Instead, we need a parser, i.e. an algorithm/program designed to parse the HTML and create a parse/syntax tree of the HTML data.
  
3. **Extracting the Data**: Once the syntax tree is created, we need to navigate it and retrieve the information that we are interested in

To complete those steps, we need two two third-party Python libraries:
1. **[Requests](https://docs.python-requests.org/en/master/)**: a simple but powerful library for sending all kinds of HTTP requests to a web server,
  
2. **[Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)**: a library for parsing HTML and XML documents. It works with a user-selected parser to provide idiomatic ways of navigating, searching, and modifying the parse tree.
  
## Ethics of Scraping
  
Web scraping is a powerful tool that should be used responsibly. Below is a list of things to consider before you start scraping data:
  
1.	Always check the robots.txt file of the site you are about to scrape, as it contains guidelines on how bots should behave on the website.
  
2.	Do not spam the website with multiple requests in a short amount of time, as that may hurt their server(s) and/or may be classified as a DDOS attack. If you need to scrape multiple pages, you can artificially limit the rate of requests, as we will show in the code.
  
3.	Do not engage in piracy or other unauthorised commercial use regarding the data you extract.

Additionally, some companies and websites may provide the data we are interested in in a clean and concise way through an API. If a public API that provides the information we are looking for is available, web scarping should be avoided altogether.
  
If you would like to know more, I suggest reading James Densmore’s article on the [Ethics in Web Scraping](https://towardsdatascience.com/ethics-in-web-scraping-b96b18136f01).

## References
  
The complete list of reference for this tutorial is included at the end of the notebook.
