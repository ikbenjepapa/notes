# Idea on How to Pull Data from AJAX Data

## Frontend Automation with Selenium

### **Use Case**
Automate interactions with a webpage if the data is loaded dynamically and requires user interaction (e.g., logging in, navigating pages).

---

### **How It Works**
- Use Selenium to log in, navigate, and scrape data from visible elements (e.g., input fields, hidden fields).
- Suitable when AJAX data or dynamic HTML is not easily accessible directly.
- **Example:** Scraping Properties TH and Properties EN using element IDs like:
  ```
  CPH_SKU_hdf_SKB_PROPERTY1_TH
  ```

---

### **Logic of the Flow**
1. **Set Up the Environment**
   - Use `webdriver.[your browser]()` to handle the environment.

2. **Provide the Webpage URL**
   - Navigate to the target webpage where data is to be scraped.

3. **Define Variables**
   - Set the variables to extract the data. For example:
     ```python
     properties = []
     ```

4. **Loop Through Elements**
   - Use a `for` loop to iterate over the TH properties:
     ```python
     for i in range(1, 11):
         element_id = f"CPH_SKU_hdf_SKB_PROPERTY{i}_TH"
     ```

5. **Handle Missing Properties**
   - Use a `try...except` block to ensure the script doesn't break if an element is missing:
     ```python
     try:
         # Your scraping logic here
     except Exception as e:
         print(f"Error: {e}")
     ```

6. **Extract and Display Data**
   - Use the `print(properties)` command to output the extracted data.

---

### **Example Code**
```python
from selenium import webdriver

# Initialize WebDriver
browser = webdriver.Chrome()
url = "https://example.com"
browser.get(url)

# Data extraction logic
properties = []
for i in range(1, 11):
    element_id = f"CPH_SKU_hdf_SKB_PROPERTY{i}_TH"
    try:
        element = browser.find_element_by_id(element_id)
        properties.append(element.text)
    except Exception as e:
        print(f"Error retrieving element {element_id}: {e}")

# Display results
print(properties)
```
