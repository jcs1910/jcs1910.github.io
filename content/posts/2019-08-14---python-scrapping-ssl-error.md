---
title: "[Python Scraping] SSL: CERTIFICATE_VERIFY_FAILED Error Solved"
date: "2019-08-15T21:35:11.199Z"
template: "post"
draft: false
slug: "/posts/python-scraping-ssl-error/"
category: "Python-scrapping"
tags:
  - "Python"
  - "Scrapping"
  - "Crawling"
  - "SSL"
  - "CERTIFICATE_VERIFY_FAILED"

description: "[URLError: <urlopen error [SSL: CERTIFICATE_VERIFY_FAILED]
certificate verify failed:"
---

<figure>
    <img src="/media/nature-photo1.jpeg" alt="unsplash-film">
    <!-- <figcaption>Splendid</figcaption> -->
</figure>

I was practicing python scraping with urllib library to get data impossible to extract from `request library`, but was faced with following code errors.

```
[URLError: <urlopen error [SSL: CERTIFICATE_VERIFY_FAILED]
certificate verify failed:
unable to get local issuer certificate (_ssl.c:1056)>
```

As always, I tried to figure out what caused this error. Many encountered such scraping error and suggested various solutions on Stackoverflow.

- [https://stackoverflow.com/questions/27835619/urllib-and-ssl-certificate-verify-failed-error](https://stackoverflow.com/questions/27835619/urllib-and-ssl-certificate-verify-failed-error)

Thing is none of these suggestions worked for me. I don't want to reinvent the wheel so I googled SSL and CERTIFICATE_VERIFY_FAILED to figure out the fundamental error issue and found out why this error happened.

## Background information

The Python standard library has multiple modules such as `httplib, urllib, urllib2,` and `xmlrpclib.` While these modules support HTTPS connections, they traditionally performed no verification of cerficiates presetend by HTTPS servers and were vulnerable to numerous attacks including Man-In-The-Middle(MITA) which hijack HTTPS connections from Python clients to eavesdrop or modify transferred data. The implications are that you need to take action to address the issue. Luckily, Python developers addressed the problem by enabling certificate verification by default. The change was implemented via Python Enhancement Proposal PEP 476.

## Solution

As suggested, I imported ssl and added `ssl._create_unverified_context()` which works like charm.

```python
from urllib.request import urlopen
from bs4 import BeautifulSoup
import ssl

context = ssl._create_unverified_context()
res = urlopen("https://seeko.kr/zboard4/zboard.php?id=mainnews",
              context=context)
soup = BeautifulSoup(res, "html.parser")
data = soup.findAll("td", "article_subject")

for item in data:
	print(item.get_text())
```

---

> **We are creating wealth every time we write a code**
