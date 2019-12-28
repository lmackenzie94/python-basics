### Webscraping

```python
pip install requests
```

```python
import requests
# used for downloading webpages/files
# only ideal if you have exact URL, and no logging in required
```

```python
res = requests.get('https://automatetheboringstuff.com/files/rj.txt')
res.status_code
res.raise_for_status() # will raise an exception if download failed
```

```python
print (res.text[:500])
```

    The Project Gutenberg EBook of Romeo and Juliet, by William Shakespeare

    This eBook is for the use of anyone anywhere at no cost and with
    almost no restrictions whatsoever.  You may copy it, give it away or
    re-use it under the terms of the Project Gutenberg License included
    with this eBook or online at www.gutenberg.org/license


    Title: Romeo and Juliet

    Author: William Shakespeare

    Posting Date: May 25, 2012 [EBook #1112]
    Release Date: November, 1997  [Etext #1112]

    Language: Eng

```python
res = requests.get('https://automatetheboringstuff.com/files/rj.txt')
playFile = open('RomeoAndJuliet.text', 'wb') #wb = write-binary mode
for chunk in res.iter_content(100000): #100,000 bytes per chunk
    playFile.write(chunk)
```

```python
playFile.close()
```

#### Parsing HTML with the Beautiful Soup module

```python
pip install beautifulsoup4
```

```python
import bs4, requests
```

```python
result = requests.get('https://forecast.weather.gov/MapClick.php?lat=34.09577230000008&lon=-118.41512149999994#.XgfK-hdKh24')
result.raise_for_status()
soup = bs4.BeautifulSoup(result.text, 'html.parser')
elems = soup.select('#current_conditions-summary > p.myforecast-current-lrg')
elems[0].text.strip()
```

    '59°F'

#### Selenium

- allows you to control the browser

```python
pip install selenium
```

```python
from selenium import webdriver
```

```python
browser = webdriver.Firefox()
browser.get('https://automatetheboringstuff.com')
elem = browser.find_element_by_css_selector('body > div.main > div:nth-child(1) > ul:nth-child(24) > li:nth-child(1) > a')
# to get multiple elements:
# browser.find_elements_by_css_selector('p')
elem.click()
```

- To type in an input, call the send_keys('text') function on the input field
- The submit() function will find the associated form and submit (no clicking needed)

```python
# Other methods
.back()
.forward()
.refresh()
.quit()
```
