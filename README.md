# woocommerce-image-remove.bg-downloader
Use this script to connect to the woocommerce api, download and rename images according to product or variation names and remove backgrounds. It will resize all the images to 500x500 squares with whitespace added to keep aspect ratio.

README.md

Title: woocommerce-image-remove.bg-downloader

Purpose:

This Python script integrates with your WooCommerce store and the Remove.bg API to automate the process of removing backgrounds from product images. Here's what it does:

Connects to Your Store: Establishes a secure connection with your WooCommerce installation.
Retrieves Product Images: Fetches images for both products and their variations.
Removes Backgrounds: Leverages the Remove.bg API to seamlessly remove backgrounds from product images.
Saves Processed Images: Stores the images with transparent backgrounds in a designated output folder.
How It Works

Configuration:

Replace the placeholder values for WOOCOMMERCE_URL, WOOCOMMERCE_CONSUMER_KEY, WOOCOMMERCE_CONSUMER_SECRET with your actual WooCommerce store's URL and API keys.
Replace the REMOVEBG_API_KEY placeholder with your own Remove.bg API key.
Connection and Validation

The preconnect_and_validate() function tests connections to both your WooCommerce store and the Remove.bg API.
Product and Image Retrieval

The retrieve_and_process_products() function fetches product data (including variation data) from your WooCommerce store.
The process_product_images() function iterates through each product and variation.
Image Download and Processing

The download_and_process_image() function (using asynchronous operations for efficiency) downloads each image.
Downloaded images are processed using the Pillow library to ensure they are square and appropriately sized.
Processed images are sent to the remove_background() function.
Background Removal

The remove_background() function interacts with the Remove.bg API to remove the background from the image.
Saving Images

Images with transparent backgrounds are saved with descriptive filenames in your specified output_folder.
Prerequisites:

A WooCommerce store with an active API.
A Remove.bg account with an API key.
Python 3 environment
Required Python libraries: requests, PIL (Pillow), aiohttp, alive_progress . Install these using pip install requests PIL aiohttp alive_progress.
To Run the Script:

Ensure you have replaced the placeholder API keys.
Create the designated output_folder if it doesn't exist.
Execute the Python script from your terminal: python your_script_name.py
Important Notes:

The script uses a progress bar (alive_progress) to visually track its progress.
Logging is included for basic debugging.

