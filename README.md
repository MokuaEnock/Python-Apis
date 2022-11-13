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

## JSON vs XML

Most data from APIs come in JSON or XML format:

- JSON stands for Javascript Object Notation
- XML stands for Extensible Markup Language.
  JSON is especially great for representing and accessing complicated data hierarchies, like this Wikipedia info box.

<pre>
<code>
    {
    "Directed by": "Steven Spielberg",
    "Produced by": [
        "Kathleen Kennedy",
        "Steven Spielberg"
    ],
    "Written by": "Melissa Mathison",
    "Starring": [
        "Dee Wallace",
        "Henry Thomas",
        "Peter Coyote",
        "Robert MacNaughton",
        "Drew Barrymore"
    ],
    "Music by": "John Williams",
    "Cinematography": "Allen Daviau",
    "Edited by": "Carol Littleton",
    "Production company": "Amblin Productions",
    "Distributed by": "Universal Pictures",
    "Release": [
        {
        "Date": "May 26, 1982",
        "Location": "Cannes"
        },
        {
        "Date": "June 11, 1982",
        "Location": "United States"
        }
    ],
    "Running time": "114 minutes",
    "Country": "United States",
    "Language": "English",
    "Budget": 10500000,
    "Box office": 792900000
    }
</code>
</pre>

## JSON Structure

JSON is built on two key structures:

## JSON Objects

- JSON objects are a collection of key: value pairs, e.g. key is "Directed by" and the value is "Steven Spielberg" that are surrounded by curly braces.
- In Python, JSON objects are interpreted as dictionaries and you can access them like you would a standard Python Dict.
- JSON object keys must be strings

## JSON Arrays

- A JSON array is an ordered list of values, e.g.the array of producers, ["Kathleen Kennedy", "Steven Spielberg" ] surrounded by square brackets.
- In Python, JSON arrays are interpreted and accessed like lists.

The values for both JSON objects and arrays can be any valid JSON data type: string, number, object, array, Boolean or null.

When objects and arrays are combined, it is called nesting.

## Accessing JSON files in Python

JSON files can be accessed in Python just like dictionaries and lists because JSON objects are interpreted as dictionaries and JSON arrays are interpreted as lists.

<pre>
    <code>
infobox_json['Box office']
infobox_json['Produced by'][0]
infobox_json['Release'][1]['Location']
    </code>
</pre>



## References

MediaWiki API =>

WPtools for Mediawiki API => https://github.com/siznax/wptools
Twitter API Tweepy =>
