# Overheid.nlDownloadPDFsAutomatically
Automatically Download All PDFs from "Officiële Bekendmakingen (Overheid.nl)"

The provided code is a Python script that is used to download PDF files from a website called Overheid.nl. The script has been written with the help of ChatGPT (3.5). 

Here is an overview of how the code works:

1. The script starts by importing the necessary libraries: `requests`, `BeautifulSoup`, `os`, and `urlparse`.

2. The variable `base_url` holds the base URL of the website from which PDF files are to be downloaded. It includes search parameters for filtering the results.

3. The variable `num_pages` determines the number of pages to be downloaded. You can modify this value according to your requirements.

4. The script uses a `for` loop to iterate over each page. It constructs the URL for the current page by appending the page number to the `base_url`.

5. A GET request is sent to the website using the `requests.get()` function, and the response is stored in the `response` variable.

6. The HTML content of the response is parsed using `BeautifulSoup` to create a BeautifulSoup object called `soup`.

7. The script uses `soup.find_all()` to find all the anchor tags (`<a>`) that have an `href` attribute, which typically represent links.

8. It iterates over each PDF link found on the page. If the URL of the PDF file does not start with "http://" or "https://", the script prepends the scheme (http or https) and the domain name to the URL using the `urlparse` module.

9. The script checks if the PDF URL ends with the ".pdf" extension. If it does, it sends a GET request to the PDF URL and stores the response in the `pdf_response` variable.

10. The script extracts the filename from the URL using `os.path.basename()`.

11. It saves the PDF file by opening a file with the extracted filename in write-binary mode (`"wb"`) and writing the content of the `pdf_response` to the file.

12. Finally, the script prints a message indicating the successful download of each file and prints a separator line between pages.

To use this code, you need to have the required libraries (`requests`, `BeautifulSoup`, `os`) installed in your Python environment. You can modify the `base_url` and `num_pages` variables to target the desired website and specify the number of pages to download.
