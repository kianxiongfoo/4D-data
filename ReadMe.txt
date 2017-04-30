#activate scrapy
source venv/bin/activate

#to deactivate python virtual environment:
deactivate

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

#for python to mongoDB
 python -m pip install pymongo


	

we first have to import they key for the official MongoDB repository.

sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 7F0CEB10

After successfully importing the key you will see:

gpg: Total number processed: 1
gpg:               imported: 1  (RSA: 1)

Next, we have to add the MongoDB repository details so APT will know where to download the packages from.

Issue the following command to create a list file for MongoDB.

echo "deb http://repo.mongodb.org/apt/ubuntu "$(lsb_release -sc)"/mongodb-org/3.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.0.list

After adding the repository details, we need to update the packages list.

sudo apt-get update

Now we can install the MongoDB package itself.

sudo apt-get install -y mongodb-org

After package installation MongoDB will be automatically started. You can check this by running the following command.

service mongod status

If MongoDB is running, you'll see an output like this (with a different process ID).

mongod start/running, process 1611

You can also stop, start, and restart MongoDB using the service commands. To stop MongoDB use

service mongod stop

To start MongoDB use

service mongod start


