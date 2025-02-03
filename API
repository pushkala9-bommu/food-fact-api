import requests
from bs4 import BeautifulSoup
# API endpoint for Open Food Facts
url = "https://world.openfoodfacts.org/cgi/search.pl"

# Parameters for the search
params = {
    "search_terms": "chocolate",
    "json": 1,
    "page_size": 5  # Number of products to retrieve
}

# Send a GET request to the API
response = requests.get(url, params=params)

# Check if the request was successful
if response.status_code == 200:
    data = response.json()
    products = data.get("products", [])
    
    # Print product details
    for product in products:
        print(f"Product: {product.get('product_name')}")
        print(f"Brand: {product.get('brands')}")
        print(f"Price: {product.get('price')}")
        print("------")
else:
    print(f"Failed to retrieve data. Status code: {response.status_code}")
