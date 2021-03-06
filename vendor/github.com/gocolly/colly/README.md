# Colly

Lightning Fast and Elegant Scraping Framework for Gophers

Colly provides a clean interface to write any kind of crawler/scraper/spider.

With Colly you can easily extract structured data from websites, which can be used for a wide range of applications, like data mining, data processing or archiving.

[![GoDoc](https://godoc.org/github.com/gocolly/colly?status.svg)](https://godoc.org/github.com/gocolly/colly)
[![Backers on Open Collective](https://opencollective.com/colly/backers/badge.svg)](#backers) [![Sponsors on Open Collective](https://opencollective.com/colly/sponsors/badge.svg)](#sponsors) [![build status](https://img.shields.io/travis/gocolly/colly/master.svg?style=flat-square)](https://travis-ci.org/gocolly/colly)
[![report card](https://img.shields.io/badge/report%20card-a%2B-ff3333.svg?style=flat-square)](http://goreportcard.com/report/gocolly/colly)
[![view examples](https://img.shields.io/badge/learn%20by-examples-0077b3.svg?style=flat-square)](https://github.com/gocolly/colly/tree/master/_examples)
[![Code Coverage](https://img.shields.io/codecov/c/github/gocolly/colly/master.svg)](https://codecov.io/github/gocolly/colly?branch=master)

## Features

 * Clean API
 * Fast (>1k request/sec on a single core)
 * Manages request delays and maximum concurrency per domain
 * Automatic cookie and session handling
 * Sync/async/parallel scraping
 * Caching
 * Automatic encoding of non-unicode responses
 * Robots.txt support


## Example

```go
func main() {
	c := colly.NewCollector()

	// Find and visit all links
	c.OnHTML("a[href]", func(e *colly.HTMLElement) {
		e.Request.Visit(e.Attr("href"))
	})

	c.OnRequest(func(r *colly.Request) {
		fmt.Println("Visiting", r.URL)
	})

	c.Visit("http://go-colly.org/")
}
```

See [examples folder](https://github.com/gocolly/colly/tree/master/_examples) for more detailed examples.


## Installation

```
go get -u github.com/gocolly/colly/...
```


## Bugs

Bugs or suggestions? Visit the [issue tracker](https://github.com/gocolly/colly/issues) or join `#colly` on freenode


## Other Projects Using Colly

Below is a list of public, open source projects that use Colly:

 * [greenpeace/check-my-pages](https://github.com/greenpeace/check-my-pages) Scraping script to test the Spanish Greenpeace web archive

If you are using Colly in a project please send a pull request to add it to the list.

## Contributors

This project exists thanks to all the people who contribute. [[Contribute]](CONTRIBUTING.md).
<a href="https://github.com/gocolly/colly/graphs/contributors"><img src="https://opencollective.com/colly/contributors.svg?width=890" /></a>


## Backers

Thank you to all our backers! 🙏 [[Become a backer](https://opencollective.com/colly#backer)]

<a href="https://opencollective.com/colly#backers" target="_blank"><img src="https://opencollective.com/colly/backers.svg?width=890"></a>


## Sponsors

Support this project by becoming a sponsor. Your logo will show up here with a link to your website. [[Become a sponsor](https://opencollective.com/colly#sponsor)]

<a href="https://opencollective.com/colly/sponsor/0/website" target="_blank"><img src="https://opencollective.com/colly/sponsor/0/avatar.svg"></a>
<a href="https://opencollective.com/colly/sponsor/1/website" target="_blank"><img src="https://opencollective.com/colly/sponsor/1/avatar.svg"></a>
<a href="https://opencollective.com/colly/sponsor/2/website" target="_blank"><img src="https://opencollective.com/colly/sponsor/2/avatar.svg"></a>
<a href="https://opencollective.com/colly/sponsor/3/website" target="_blank"><img src="https://opencollective.com/colly/sponsor/3/avatar.svg"></a>
<a href="https://opencollective.com/colly/sponsor/4/website" target="_blank"><img src="https://opencollective.com/colly/sponsor/4/avatar.svg"></a>
<a href="https://opencollective.com/colly/sponsor/5/website" target="_blank"><img src="https://opencollective.com/colly/sponsor/5/avatar.svg"></a>
<a href="https://opencollective.com/colly/sponsor/6/website" target="_blank"><img src="https://opencollective.com/colly/sponsor/6/avatar.svg"></a>
<a href="https://opencollective.com/colly/sponsor/7/website" target="_blank"><img src="https://opencollective.com/colly/sponsor/7/avatar.svg"></a>
<a href="https://opencollective.com/colly/sponsor/8/website" target="_blank"><img src="https://opencollective.com/colly/sponsor/8/avatar.svg"></a>
<a href="https://opencollective.com/colly/sponsor/9/website" target="_blank"><img src="https://opencollective.com/colly/sponsor/9/avatar.svg"></a>


