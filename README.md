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

## Storing Data

Storing is usually done after cleaning, but it's not always done, which excludes it from being a core part of the data-wrangling process. Sometimes you just analyze and visualize and leave it at that, without saving your new data.

Again, because storing is performed on cleaned data, we could cover this at the end of Lesson 4 ("Cleaning Data"). But since we're covering file formats in this lesson, let's cover it here.

Imagine you've assessed and cleaned your data, which includes merging all of these separate pieces of data, which as I mentioned in the last video I took care of behind the scenes for you. What do you want to do next?

## Relational Database Structure

A database is an organized collection of data that is structured to facilitate the storage, retrieval, modification, and deletion of data. There are two main types of databases: relational databases and non-relational databases, with relational being the most popular. SQL, or Structured Query Language, is the standard language for communicating with relational databases.

The most common way of accessing data and databases today is via SQL or structured query language. SQL has several functions that allow users to easily read, manipulate and change data. SQL is also popular for data analysis because:

- It's easy to understand and learn
- It can access data directly from where it's stored
- It's easy to audit and replicates
- It can run queries on multiple tables at once, across large datasets
- It can answer complex questions with more detail and depth compared to other analytic tools
  Most applications need to store information so that it may be accessed later and this is the function of a database. SQL is the language that allows analysts and others to access this information.

Databases have many advantages:

- They check for data integrity, to make sure data is entered in the appropriate format
- They are fast across large datasets and can be optimized for greater speed
- They are shared entities, meaning many people can access the same data at the same time
- They have administrative features like access controls

Database tables are organized by column :

- Each column has a unique name
- All the data in a column must be the same data type
- Descriptive column names are important

## Types of SQL statements

SQL has a few basic elements that are important to remember:

- `statement` - a piece of correctly written SQL code to tell the database what you want to do
- `CREATE` - creates a new table in the database
- `DROP TABLE`- removes a table from the database
- `SELECT` - allows you to read and display data, aka Queries
- `FROM` - What data do you want to pull from? What table of data do you want to use?
- `SELECT` - Which elements from the database do you want to pull? What columns do you want to pull from that table?

## Data Wrangling and Relational Databases

In the context of data wrangling, we recommend that databases and SQL only come into play for gathering data or storing data. That is:

- *Connecting to a database and importing data* into a pandas DataFrame (or the analogous data structure in your preferred programming language), then assessing and cleaning that data, or
- *Connecting to a database and storing data* you just gathered (which could potentially be from a database), assessing, and cleaning

These tasks are especially necessary when you have large amounts of data, which is where SQL and other databases excel over flat files.

The two scenarios above can be further broken down into three main tasks:

- Connecting to a database in Python
- Storing data from a pandas DataFrame in a database to which you're connected, and
- Importing data from a database to which you're connected to a pandas DataFrame

1. Connect to a database. We'll connect to a SQLite database using SQLAlchemy, a database toolkit for Python.
2. Store the data in the cleaned master dataset in that database. We'll do this using pandas' `to_sql` DataFrame method.
3. Then read the brand new data in that database back into a pandas DataFrame. We'll do this using pandas' `read_sql` function

## References

MediaWiki API =>

WPtools for Mediawiki API => https://github.com/siznax/wptools
Twitter API Tweepy =>
