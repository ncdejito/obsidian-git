[[Data Analysis]]

Web scraping - beautiful soup, selenium
LLM for creating scrape pipelines for websites
https://www.linkedin.com/posts/dat-tran-a1602320_scrapegraphai-you-only-scrape-once-activity-7209116059583283202-jPYM?utm_source=share&utm_medium=member_desktop

Download from gdrive using

```
wget --load-cookies /tmp/cookies.txt "https://docs.google.com/uc?export=download&confirm=$(wget --quiet --save-cookies /tmp/cookies.txt --keep-session-cookies --no-check-certificate 'https://docs.google.com/uc?export=download&id=**FILEID**' -O- | sed -rn 's/.*confirm=([0-9A-Za-z_]+).*/\1\n/p')&id=**FILEID**" -O **FILENAME** && rm -rf /tmp/cookies.txt
```