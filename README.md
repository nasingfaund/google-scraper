<h1 align="center">
Google Scraper
</h1>

The truth is, scraping is something you are probably familiar with. Everyday, millions of people go on a search engine like Google to look up some information of particular interest. Now, if you were to copy and paste some of the results you get onto a document, then you are scraping the web for information. 

But, in a technical sense, what is web scraping? Web scraping involves using a web scraper software to automate the routine process of gathering valuable information from third-party sites. In most cases, this involves you making a request to a particular web page, and then reading and parsing the data from the HTML or XHTML code to a machine-readable format like XML or JSON. In this article, we’ll show you how to build a scraping tool with Python. Using this tool, you’ll be able to acquire data from Google and several other search engines.


## Table of Contents 
- [Google Scraper features](#google-scraper-features)
- [What kind of data can you get using Google Scraper?](#what-kind-of-data-can-you-get-using-google-scraper)
- [Top use cases](#top-use-cases)
- [How does Google Scraper bypass the restrictions against scraping?](how-does-google-scraper-bypass-the-restrictions-against-scraping)
- [How to overcome the difficulties of browserless scraping](how-to-overcome-the-difficulties-of-browserless-scraping)
- [Google Scraper Installation](#google-scraper-installation)
  - [Installation on Windows](#installation-on-windows)
  - [Installation on Linux](#installation-on-linux)
- [Configuration](#installation)
- [How to use Google Scraper](#how-to-use-google-scraper)
- [Testing Google Scraper](#testing-google-scraper) 

## Google Scraper features 

There are two approaches to how Google Scraper works: 
- Scraping is done using low-level HTTP libraries, such as urllib.request or requests modules. This mimics the HTTP packets transmitted by real browsers.
- Scraping is accomplished using the Selenium framework to control a real browser. 

The second approach is more reliable because search engines can’t easily detect it.

#### Google Scraper has the following features:
- It has been built for Python.
- It makes use of multithreading and asynchronous input/output.
- It enables concurrent scraping through many IP addresses (proxies).
- It supports proxy connections using socksipy and built-in browser proxies:
  - SOCKS5
  - SOCKS4
  - HTTP Proxy
- It supports different search modes such as news, images, and video.

## Top use cases 

Google Scraper extracts and parses search engine results, including all the detected links, titles, and descriptions. Below is a list of the most common use cases for Google Scraper: 

- Collecting a large number of Google dorks in a short period of time.
- Utilizing it as a part of a search engine optimization technique.
- Investigating trends.
- Compiling a list of websites to incorporate into your own database.
- Numerous additional applications. 
- Extensible quite easily due to the well-documented code. 

## How Google Scraper bypasses the restrictions against scraping

There are several ways search engines can detect robotic behavior. For example: 

- The User-Agent given by the client indicates a software program that is not a browser.

- The request parameters are not formatted the same as if a human was to use a browser to carry our a search:
  - On the client-side, running JavaScript could mean running additional bot detection tools.Heuristics that attempt  detect human behavior may fall under this    category. For instance, only humans usually move the cursor and hover over the search results, which is what robots typically don’t do. 
  
- Bots have a precise request pattern and their robotic behavior can be well anticipated. Humans’ behavior, on the other hand, is not easily predicted.

- Certain JavaScript scripts are triggered when the search engine loads images, audio, etc. If JavaScript doesn’t function properly, the search engine clearly understands that no pictures/ads/CSS/JavaScript are loaded; this could be attributed to the client being a robot-run script, which rarely processes JavaScript.

As a result, the most difficult obstacles to overcome are the algorithms that use JavaScript actions. Google Scraper takes the approach of scraping based on emulating browsers in a browser-like environment capable of executing JavaScript. 

Each of these virtual browsers' networking is proxied and tweaked to make it behave like an actual user. Without utilizing too much of the system's resources, it should be possible to handle 20 browser sessions parallelly. However, the real problem will always be the lack of efficient proxies.

## How to overcome the difficulties of browserless scraping
 
When scraping with urllib.request or requests modules, there are various drawbacks.

Browsers are complicated software systems of enormous magnitude. Firefox contains over 10 million lines of code, whereas Chrome has roughly 8 million. Companies pour significant resources into pushing technology ahead and have a distinct browser experience.

As a result, the replication of such a browser is essentially impossible with just HTTP requests. Google provides multiple options for detecting irregularities and problems in internet browsing. It is impossible to scrape without being detected using just the dynamic nature of JavaScript. With that said, scraping requires an alternative technique that employs Python to automate a real browser. 

To optimize performance, the most advantageous choice is to use the Chrome browser, because Google's native browser is likely to have optimizations applied to make browsing Google's own sites more performant. 

What is more, the Google Scraper runs multiple Chrome instances that are controlled independently. Each instance can have its own proxy defines. The performance grows linearly as more instances are run as long as there are enough system resources.

The technologies that perform the automation are:
- [Selenium](https://pypi.org/project/selenium/)
- [Mechanize](http://wwwsearch.sourceforge.net/mechanize/)

# Google Scraper Installation

## Prerequisites
 
- Knowledge of Python 3.x
- Knowledge of Scraping
- Knowledge of Selenium

## Installation on Windows 

Python 3.x Installation

Use the Python 3.7+ distribution of your choice. You can download Python 3.x from the official repository or install Anaconda distribution. 
After installation verify the python version by running the python command: 
``` 
C:\dev>python3 --version
Python 3.9.6
```

Create Python Virtual Environment: 
```C:\dev>python -m venv venv```

Activate Virtual Environment: 
```
C:\dev>C:\dev\venv\Scripts\activate
(venv) C:\dev> 
```

## Installation on Linux

Python 3.x Installation

Most of the Linux distros come loaded with Python 3.x and Python 2.x. Nonetheless, you can check the Python version by simply running the ```python3``` command in the console. 

You can download Python 3.x from [this link](https://www.python.org/downloads/source/) or install the [Anaconda distribution.](https://www.anaconda.com/products/individual)

After installation verify the python version by running the Python command:
```
$ python3 --version
Python 3.9.6
````
Create Python Virtual Environment: 
```$ python3 -m venv venv```

Activate Virtual Environment: 
```$ source venv/bin/activate```

## Install Google Scraper using Pip

Use Pip to install Google Scraper: 

```$ pip install GoogleScraper```

## Install Google Scraper using GitHub

You can install Google Scraper from the latest source that resides in this GitHub repository. 

```$ pip install git+git://github.com/NikolaiT/GoogleScraper/``` 

## Configuration

### Download Chromedriver 

Download the latest Chromedriver if you are going to use Chrome as your browser [here.](https://sites.google.com/a/chromium.org/chromedriver/downloads)

Unzip the driver and save it somewhere and then update the ```chromedriver_path``` in the Google Scraper configuration file ``` scrape_config.py``` to the path where you saved the driver ```chromedriver_path = 'Drivers/chromedriver'```

### Download Geckodriver

Download the latest geckodriver if you are going to use Firefox as your browser [here.](https://github.com/mozilla/geckodriver/releases)

Unzip the driver and save it somewhere and then update the ```geckodriver_path``` in the Google Scraper configuration file ```scrape_config.py``` to the path where you saved the driver ``` geckodriver_path = 'Drivers/geckodriver'```

### Update the Settings for Selenium and Browsers

Update the following settings in the GoogleScraper configuration file ```scrape_config.py``` to your values as shown below: 

```
# chrome driver executable path
# get chrome drivers here: https://chromedriver.storage.googleapis.com/index.html?path=2.41/
chromedriver_path = 'Drivers/chromedriver'

# geckodriver executable path
# get gecko drivers here: https://github.com/mozilla/geckodriver/releases
geckodriver_path = 'Drivers/geckodriver'

# path to firefox binary
firefox_binary_path = '/home/nikolai/firefox/firefox'

# path to chromium browser binary
chrome_binary_path = '/usr/bin/chromium-browser'
```
scraper_config.py

Now it is quite possible you might encounter KeyError when you run any particular command as shown below:
```
scraper) C:\dev>python3 -m GoogleScraper -h
Traceback (most recent call last):
  File "c:\dev\scraper\lib\site-packages\sqlalchemy\sql\base.py", line 1201, in __getattr__
    return self._index[key]
KeyError: '_data'
```
KeyError

To resolve the error, uninstall sqlalchemy and install the sqlalchemy version 1.3.24 . The above error is caused by version>1.4. 
```(venv) C:\dev>pip uninstall sqlalchemy```

Uninstall existing sqlalchemy module: 
```(venv) C:\dev>pip install sqlalchemy==1.3.24```

Install sqlalchemy version 1.3.24. 

### Install sqlalchemy version 1.3.24
 
Create a SearchData folder. This folder would contain the text files. The text files will contain the search keywords. You can also download sample files from the GitHub [link.](https://github.com/NikolaiT/GoogleScraper)

### Create Output Folder
 
Create an Output Folder that will contain the scraped data. The output can be either in JSON or CSV format. 

Open the ```scrape_config.py``` file and provide the path to your output folder and file name. The scraping tool will create the file with that name. 

```output_filename = '/home/user/output/sample.json'``` 

## How to use Google Scraper

### Using Through Command Line
 
Scraping can be done in synchronous and asynchronous mode. Once all the configurations have been done, the scraping tasks can be performed. Here are some of the scraping tasks you can do at this stage. The ideal way to use Google Scraper is through command line:

```
$ python3 -m GoogleScraper --keyword-file /tmp/keywords --search-engine google --num-pages-for-keyword 3 --scrape-method selenium
``` 

The command-line script above ```--scrape-method selenium``` means that GoogleScraper.py will scrape using real web browsers. This is quite strong, as it allows you to scrape lengthy and numerous websites. The parameter ```--keyword-file``` must be a file containing keywords separated by newlines. Thus, one line for each Google query. The parameter ```--num-pages-for-keyword``` allows GoogleScraper to fetch 3 consecutive pages for each keyword.

### Database creation

Following the scraping, a new sqlite3 database named google scraper.db will be created in the same directory. The following command will open the database: 

```$ python3 -m GoogleScraper --shell```

Google search scraping 10,000 keywords in two hours can be done easily using Google Scraper. You can increase the maximum number of browsers in the configuration file.
 
### Using Proxy File

If desired, you can supply the ```--proxy-file``` flag as an argument; in this case, you have to pass a file containing proxies. The following is the format of the file:

```protocol proxyhost:proxyport username:password (...)```

For example, you can pass the file in the format as shown here:

```
socks5 127.0.0.1:8080 asb:435qg
socks4 79.86.59.24:1080 bcsd:js@abc(ad3)
```

### Using Google Scraper in HTTP mode

To use Google Scraper in HTTP mode, (raw headers will be sent) refer to the following script:

```$ python3 -m GoogleScraper -m http -p 1 -n 25 -q "blue light filter"```

### Searching for a keyword 

The task below will search for the keyword “apple” and write the output in the output folder. 

```$ python3 -m GoogleScraper -m http --keyword "apple" -v info```

### Scrape all keywords that are in the file in headless mode

Following script scrapes data using Selenium in Chrome browser in headless mode. The scraping is done using keywords provided in the text file called 5words.txt under the SearchData folder.

```$ python3 -m GoogleScraper -m selenium --sel-browser chrome --browser-mode headless --keyword-file SearchData/5words -v info```

You can scrape in the following manner:

- Provide keywords in a text file
- Scrape with HTTP mode
- Scrape by using 5 threads
- Scrape Bing and Yahoo search engines

```
$ python3 -m GoogleScraper -m http --keyword-file SearchData/some_words.txt --num-workers 5 --search-engines "bing,yahoo" --output-filename threaded-results.json -v debug
```

The above script uses keywords from the text file and scrapes the data from specific search engines i.e., Bing and Yahoo. The output is stored in a JSON file while the verbosity level is set to debug.

### Searching for an image

The below task will search an image based on a “K2 mountain” keyword. 

```$ python3 -m GoogleScraper -s "google" -q "K2 mountain" -t image -v info```

The output can be stored in a JSON file. Also, the verbosity level can be set to debug level in the Google Scraper.

### Sample Keywords based text file
 
The following file can be considered as a reference for providing keywords:

```
keyword number one
how to become a good dancer
inurl:"index.php?sl=43"
filetype:.cfg
allintext:"Founder of Apple Company"
intitle:"admin config"
Best hotels in london
```

### Asynchronous Task
 
The below task uses marketing-models-brands.txt file. This text file consists of all the keywords that are going to be scraped. By default, asynchronous mode spawns 100 requests at the same time, which translates to around 100 requests per second. The scraped data is written in marketing.json. To write the output, result -o parameter is given.

```
$ python3 -m GoogleScraper -s "bing,yahoo" --keyword-file SearchData/marketing-models-brands.txt -m http-async -v info -o marketing.json
```

## Testing Google Scraper

You can test the Google Scraper by running the following script:

```
$ python3 -m pytest Tests/functional_tests.py::GoogleScraperMinimalFunctionalTestCase
```

If no output file is mentioned, then Google Scraper will not write to any output file. However, the scraped data will be stored in sqlite database and in the directory where Google Scraper is called from. 

### Command Usage

```$ python3 -m GoogleScraper -h```

Displays all the options with arguments. 

```
GoogleScraper -h
usage: GoogleScraper [-h] [-m {http,selenium,http-async}] [--sel-browser {firefox,chrome}]
                     [--browser-mode {normal,headless}] [-q KEYWORD | --keyword-file KEYWORD_FILE]
                     [-o- OUTPUT_FILENAME] [--shell] [-n NUM_RESULTS_PER_PAGE] [-p NUM_PAGES_FOR_KEYWORD]
                     [-z NUM_WORKERS] [-t SEARCH_TYPE] [--proxy-file PROXY_FILE] [--config-file CONFIG_FILE]
                     [--check-detection CHECK_DETECTION] [--simulate]
                     [-v {debug,info,warning,warn,error,critical,fatal}] [--print-results {all,summarize}]
                     [--view-config] [-V] [--clean] [--mysql-proxy-db MYSQL_PROXY_DB] [-s SEARCH_ENGINES]

Scrapes Google, Yandex, Bing and many other search engines by forging HTTP requests that imitate browser searches or by using real browsers controlled by the Selenium framework. Multithreading support.

Optional arguments:

  -h, --help            show this help message and exit
  -m {http,selenium,http-async}, --scrape-method {http,selenium,http-async}
                        The scraping type. There are currently three types: "http", "selenium" and "http-async".
                        "Http" scrapes with raw http requests, whereas "selenium" uses the selenium framework to
                        remotely control browsers. "http-async" makes use of gevent and is well suited for extremely
                        fast and explosive scraping jobs. You may search more than 1000 requests per second if you
                        have the necessary number of proxies available.
  --sel-browser {firefox,chrome}
                        The browser frontend for selenium scraping mode. Takes only effect if --scrape-method is set
                        to "selenium"
  --browser-mode {normal,headless}
                        In which mode the browser is started. Valid values = (normal, headless)
  -q KEYWORD, --keyword KEYWORD
                        The search keyword to scrape for. If you need to scrape multiple keywords, use the --keyword-
                        file flag
  --keyword-file KEYWORD_FILE
                        Keywords to search for. One keyword per line. Empty lines are ignored. Alternatively, you may
                        specify the path to an python module (must end with the .py suffix) where the keywords must be
                        held in a dictionary with the name "scrape_jobs".
  -o- OUTPUT_FILENAME, --output-filename OUTPUT_FILENAME
                        The name of the output file. If the file ending is "json", write a json file, if the ending is
                        "csv", write a csv file.
  --shell               Fire up a shell with a loaded sqlalchemy session.
  -n NUM_RESULTS_PER_PAGE, --num-results-per-page NUM_RESULTS_PER_PAGE
                        The number of results per page. Must be smaller than 100, by default 50 for raw mode and 10
                        for selenium mode. Some search engines ignore this setting.
  -p NUM_PAGES_FOR_KEYWORD, --num-pages-for-keyword NUM_PAGES_FOR_KEYWORD
                        The number of pages to request for each keyword. Each page is requested by a unique connection
                        and if possible by a unique IP (at least in "http" mode).
  -z NUM_WORKERS, --num-workers NUM_WORKERS
                        This arguments sets the number of browser instances for selenium mode or the number of worker
                        threads in http mode.
  -t SEARCH_TYPE, --search-type SEARCH_TYPE
                        The searchtype to launch. May be normal web search, image search, news search or video search.
  --proxy-file PROXY_FILE
                        A filename for a list of proxies (supported are HTTP PROXIES, SOCKS4/5) with the following
                        format: "Proxyprotocol (proxy_ip|proxy_host):Port "Example file: socks4 127.0.0.1:99 socks5
                        33.23.193.22:1080
  --config-file CONFIG_FILE
                        The path to the configuration file for GoogleScraper. Normally you won't need this, because
                        GoogleScrape comes shipped with a thoroughly commented configuration file named
                        "scrape_config.py"
  --check-detection CHECK_DETECTION
                        Check if the given search engine blocked you from scrapign. Often detection can be
                        determinedif you have to solve a captcha.
  --simulate            If this flag is set, the scrape job and its estimated length will be printed.
  -v {debug,info,warning,warn,error,critical,fatal}, --verbosity {debug,info,warning,warn,error,critical,fatal}, --loglevel {debug,info,warning,warn,error,critical,fatal}
                        Set the debug level of the application. Use the string representation instead of the numbers.
                        High numbers will output less, low numbers more. CRITICAL = 50, FATAL = CRITICAL, ERROR = 40,
                        WARNING = 30, WARN = WARNING, INFO = 20, DEBUG = 10, NOTSET = 0
  --print-results {all,summarize}
                        Whether to print all results ("all"), or only print a summary ("summarize")
  --view-config         Print the current configuration to stdout. You may use it to create and tweak your own config
                        file from it.
  -V, --v, --version    Prints the version of GoogleScraper
  --clean               Cleans all stored data. Please be very careful when you use this flag.
  --mysql-proxy-db MYSQL_PROXY_DB
                        A mysql connection string for proxies to use. Format:
                        mysql://<username>:<password>@<host>/<dbname>. Has precedence over proxy files.
  -s SEARCH_ENGINES, --search-engines SEARCH_ENGINES
                        What search engines to use (See GoogleScraper --config for the all supported). If you want to
                        use more than one at the same time, just separate with commatas: "google, bing, yandex". If
                        you want to use all search engines that are available, give '*' as argument.

GoogleScraper 0.2.4. This program might infringe the TOS of the search engines. Please use it on your own risk. (c) by
Nikolai Tschacher, 2012-2018. incolumitas.com
``` 
