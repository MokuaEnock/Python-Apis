# Accessing data through APIs in python
## Introduction

APIs give you relatively easy access to data from the Internet. Twitter, Facebook, and Instagram all have APIs and there are many open-source APIs.

Scraping is brittle and breaks with web layout redesigns because the underlying HTML has changed.

APIs and their access libraries allow programmers to access data in a super simple manner. `rtsimple` is an access library for Rotten Tomatoes that uses Python. If we had permission to use the Rotten Tomatoes API, we could import `rtsimple`, use our API key, create an object for each movie and access the rating data directly from the movie object.

## MediaWiki API
MediaWiki has a great tutorial on their website on how their API calls are structured. It's a nice and simple example and they explain the various moving parts:

- The endpoint (important takeaway: there is nothing special about this URL!)
- The format
- The action
 -Action-specific parameters
Go and read that example and then come back to the classroom.

Done reading? Great! Though they say that is a "simple example," it could be simpler! This is where access libraries, also known as client libraries or even just libraries (as in "Twitter API libraries"), come into play and make our lives easier.
## References

MediaWiki API =>

WPtools for Mediawiki API => https://github.com/siznax/wptools
Twitter API Tweepy =>
