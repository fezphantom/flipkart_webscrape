# flipkart_webscrape
Problem statement: Gathering data from an E-commerce website that can be used for sentiment Analysis.

Imports
flask : Flask, render_template,request,jsonify
flask_cors:  CORS,cross_origin
requests
bs4: BeautifulSoup
urllib.request: urlopen

The project is divided into 2 parts:
1. Html
  a: Index or welcome page with 2 form inputs 'index.html':
      i : Text input which handles the search product input
      ii : The submit button
  b: Result page ('results.html')that shows the tabular display of product, customer name,etc.

2. Python script
  a: application.py: The backend and structure with 2 functions
    i : home_page function: to render the hompage 'index.html'
    ii : index function: This function pulls the content inputed into the search form and processes accordingly.
    
Index function breakdown:
  1. Gets the product name from the form.
  2. Appends product name to the website's url
  3. Get's the source code of the website.
  4. Filter out comment section.
  5. Create an empty list 'reviews'
  6. Create a for loop to run through each comment source code and extract the following details:
    a: Product name
    b: Customer name
    c. Product Rating
    d. Comment Header
    e. Comment
  7. Create a writeable file using the product_name.csv and write extracted data into file
  8. Store each extracted data in a dictionary which is appended to the 'reveiw' list after each iteration.
  9. return the list to the 'results.html' through render_template. This list will be displayed on the results.html page.
  
web_scrabing.ipynb was used to experiment the codes used for data extraction
Note: css and html were provided from a different source.
  
