# idea on how to pull data from AJAX data

// Frontend Automation with Selenium
Use Case: Automate interactions with the webpage if the data is loaded dynamically and requires user interaction (e.g., logging in, navigating pages).

How It Works:
Use Selenium to log in, navigate, and scrape data from visible elements (e.g., input fields, hidden fields).
Suitable when AJAX data or dynamic HTML is not easily accessible directly.
Example: Scraping Properties TH and Properties EN using element IDs. [CPH_SKU_hdf_SKB_PROPERTY1_TH]

logic of the flow
- use webdriver.[your browser]() to handle the environment
- provide the webpage-url
- set the varibles to extraact the data in which they are properies = []
- use **for i in range(1, 11)** to  loop the TH properties and the element would be "element_id = f"CPH_SKU_hdf_SKB_PROPERTY{i}_TH"
- then we need to handle the no info properties too. I can do a try...except block ensures the script doesn't break if an element is missing.
- use simple print(properties) command to execute the data extraction


