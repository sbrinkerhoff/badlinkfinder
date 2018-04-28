# badlinkfinder

This is a Python 3 program that recursively searches your website to find issues. It was started as an afternoon project out of my desire to explore some web crawling and indexing methodologies, and aims to be an easy tool to scan your website and locate broken assets, links, etc.

You are required to supply a `seed URL` which is where the web crawler will begin its search. In order to prevent it from crawling the entire internet, it will only stay within the initial domain provided in the seed URL. Additionally, it is smart about crawling and tries to guess the MIME type of the URL before downloading it. If it is detected to be an asset (e.g. an image or audio file), it only performs a `HEAD` request in order to save on bandwidth and processing time. 

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Support](#support)
- [Contributing](#contributing)

## Installation

This can be deployed on any OS that has Python 3 available. Simply clone this repository into a directory of your choice.
```
git clone https://github.com/Jonchun/badlinkfinder.git
```

Install Python requirements
```
pip3 install -r requirements.txt
```

## Usage
Execute as a module.

```
python3 -m badlinkfinder URL
```

Current `--help` output.
```
python3 -m badlinkfinder --help
BadLinkFinder - a recursive bot that scrapes a domain and finds all bad assets/links.

Positional Arguments:
  These arguments come after any flags and in the order they are listed here.
      Only URL is required.

  URL
      The starting seed URL to begin crawling your website. This is required to begin searching for bad links.


Crawler Settings:
  --threads THREADS
      By default, 5 threads are used for the crawler.

  --timeout TIMEOUT
      By default, requests time out after 10 seconds.

  --include_inbound
      Whether to include inbound URLs when reporting Site Errors (show where they were referenced from)


Troubleshooting:
  --help
      Show this help message and exit.

  --version
      Show version and exit.

  --verbosity VERBOSITY
      The verbosity level:
        0: NONE
        1: ERROR
        2: WARNING
        3: INFO
        4: ALL
```

## Support

Please [open an issue](https://github.com/Jonchun/badlinkfinder/issues/new) for support. This is very much a work in progress, so rapid-development will be happening.

## Contributing

Please contribute using [Github Flow](https://guides.github.com/introduction/flow/).
Create a branch, add commits, and [open a pull request](https://github.com/Jonchun/badlinkfinder/compare).