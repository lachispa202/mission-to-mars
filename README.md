## Goal

Use BeautifulSoup, Splinter, and Pandas to scrape five different webpages related to Mars, and display the results on a webpage using MongoDB and Flask. 

## Process

**Scraping Mars Data**

Scraping was first done in a Jupyter notebook to test the code as it was written. After importing the necessary dependencies, I connected to the chromedriver and set up my browser to open each webpage I needed to scrape. I first scraped the NASA Mars News website for the title and text of the most recent article, storing the results in variables to be referenced later. To do this, I used BeautifulSoup  to parse through the HTML and search for the appropriate elements and classes that contained the information I needed with `soup.find_all()`. Because the results come back as a list, I indexed the first item and took the text of that. 

The second page, was the Jet Propulsion Laboratory’s Mars page, where I would grab the full-sized featured image. This required clicking two other links after visiting the first page, so I used `browser.click_link_by_partial_text()` and `time.sleep()` to access those pages without inducing an error. Afterwards, I used `soup.find_all()` and `.a[‘href’]` to find the relative image path, which I combined with the main url to get the full-sized image. 

Third, was the Mars Weather Twitter Account, where I would grab the most recent tweet. This was done in the same manner as the first page, parsing through the HTML to find the necessary element, and then grabbing the text of that.  
