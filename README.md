# -
python練習一


import requests
from bs4 import BeautifulSoup

url = "http://www.management.ntust.edu.tw/front/bin/rcglist,7.phtml"
r = requests.get(url)

soup = BeautifulSoup(r.content)

links = soup.find_all("a")

g_data = soup.find_all("a",{"class":"shadow-link"})

for link in g_data:
    print(link.text)

#for link in g_data:
#    print(link.get("href"),link.text)

#for item in g_data:
#    print(item.content[0].text)

    
