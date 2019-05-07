![Python Version](https://img.shields.io/static/v1.svg?label=Python&message=3.x&color=Blue)
![GitHub](https://img.shields.io/github/license/spiderlabs/hosthunter.svg)
![Twitter Follow](https://img.shields.io/twitter/follow/superhedgy.svg?style=social)

HostHunter v1.5
======

A tool to efficiently discover and extract hostnames providing a large set of target IP addresses. HostHunter utilises simple OSINT techniques to map IP addresses with virtual hostnames. It generates a CSV or TXT file containing the results of the reconnaissance.

Latest version of HostHunter also takes screenshots of the targets, it is currently a beta functionality.

## Demo
* Currently GitLab's markup language does not support HTML or CSS control over the images, thus the following link thumbnail is huge.

[![asciicast](https://asciinema.org/a/jp9B0IB6BzRAgbH3iNp7cCTpt.png)](https://asciinema.org/a/jp9B0IB6BzRAgbH3iNp7cCTpt)

## Installation
* Tested with Python 3.7.2.

### Linux / Mac OS
* Install python dependencies.
```bash
$ pip3 install -r requirements.txt
```

The next few steps are only required if you would like to use the Screen Capture feature.
* Use wget command to download the latest Google Chrome Debian package.

Mac OS:
```bash
$ brew cask install google-chrome
```
or

Linux:
```bash

$ wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb

$ dpkg -i ./google-chrome-stable_current_amd64.deb

$ sudo apt-get install -f
```

* Download and install ChromeDriver.

Mac OS:
```bash
wget -O /tmp/chromedriver.zip https://chromedriver.storage.googleapis.com/74.0.3729.6/chromedriver_mac64.zip && sudo unzip /tmp/chromedriver.zip chromedriver -d /usr/local/bin/;
```
or

Linux:
```bash
wget -O /tmp/chromedriver.zip https://chromedriver.storage.googleapis.com/74.0.3729.6/chromedriver_linux64.zip && sudo unzip /tmp/chromedriver.zip chromedriver -d /usr/local/bin/;
```

## Simple Usage Example
```bash
$ python3 hosthunter.py <targets.txt>
```

```bash
$ cat vhosts.csv
```

## More Examples
HostHunter Help Page
```bash
$ python3 hosthunter.py -h
usage: hosthunter.py [-h] [-b] [-f FORMAT] [-o OUTPUT] [-sc] [-t TARGET] [-V]
                     [targets]

|<--- HostHunter v1.5 - Help Page --->|

positional arguments:
  targets               Sets the path of the target IPs file.

optional arguments:
  -h, --help            show this help message and exit
  -b, --bing            Use Bing.com search engine to discover more hostnames
                        associated with the target IP addreses.
  -f FORMAT, --format FORMAT
                        Choose between CSV and TXT output file formats.
  -o OUTPUT, --output OUTPUT
                        Sets the path of the output file.
  -sc, --screen-capture
                        Capture a screen shot of any associated Web
                        Applications.
  -t TARGET, --target TARGET
                        Scan a Single IP.
  -V, --version         Displays the currenct version.

```                        

Run HostHunter with Bing and Screen Captures modules enabled
```bash
$ python3 hosthunter.py <targets.txt> --bing -sc -f csv -o hosts.csv
```
Display Results
```bash
$ cat hosts.csv
```
View Screenshots
```bash
$ open ./screen_captures/
```

## Features
[X] Works with Python3  
[X] Scraps Bing.com results  
[X] Supports .txt and .csv output file formats
[X] Validates target IPv4 addresses  
[X] Takes Screenshots of the targets  
[X] Extracts hostnames from SSL certificates  
[X] Utilises Hacker Target API  

## Coming Next
[\_] Support for HackerTarget API key

## Notes
* Free APIs throttle the amount of requests per day per source IP address.

## License
This project is licensed under the MIT License.

## Authors
* **Andreas Georgiou** - find me on twitter - [@superhedgy](https://twitter.com/superhedgy)
