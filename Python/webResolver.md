<pre>
import requests as rq
from bs4 import BeautifulSoup

url = "https://url"
response = rq.get(url, verify=False)
html_doc = response.text
soup = BeautifulSoup(response.text, "lxml")
price = soup.find(id="id_value")
</pre>