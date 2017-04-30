#activate scrapy
source venv/bin/activate

# create crawl project
scrapy crawl <project_name> -o <filename>.json

#debug a website
scrapy shell 'http://quotes.toscrape.com/page/1/'
scrapy shell 'http://www.live4d2u.com/past-results?drawpastdate=2017-01-22'


//live4d2u scrape
response.xpath('').extract()
response.xpath('//td[@class="resulttop"]').extract()

links = response.xpath('//table[@class="resultTable"]')[0]
for td in links.xpath('.//td[@class="resulttop"]/text()'):
  print td.extract()