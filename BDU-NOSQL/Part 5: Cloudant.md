Getting Started With IBM Cloudant Script
===============================================================
Welcome to Lesson 5 of the Introducing NoSQL and Database as a Service course.
This last lesson provides you with a hands-on look at using IBM Cloudant.
This lesson shows you how to sign up for an IBM Cloudant account, view your dashboard to create a
database and add data documents, change database permissions, replicate a sample database, query
data, work with the HTTP API, and access documentation and support resources.

#### Cloudent Account
Your first step in your Cloudant journey is to sign up for a free account. Provide the requested information
to register. Your first step in your Cloudant journey is to sign up for a free account. Provide the requested
information to register. Cloudant offers a number of data centers to choose from for your account, and
recommends you choose the cluster that is geographically closest to your application.
When you sign in, you are immediately brought to your dashboard, so your next step is to create a
database.

The database name should contain only lowercase alphanumeric characters and no spaces.

#### JSON Documents
Cloudant is a NoSQL document database meaning that a database contains a collection of JSON formatted
documents. So, to add data to your database, you add a new document to the database.

The dashboard includes an easy-to-use JSON editor that helps you ensure the documents use the correct
JSON syntax. A JSON document includes a set of key value pairs: a name and its value. When you create a
document, Cloudant automatically generates a unique document identifier, or you can provide your own.
The value of the id key is how the database system identifies each document and must be unique in each
database.

Cloudant allows you to use a flexible schema. Each document can use the same schema or use a unique
schema. The values in a document can contain numbers, strings, nested objects, arrays, or Boolean data.
Save this document, and go back to the dashboard. You’ll notice that Cloudant automatically added
another key-value pair beginning with rev which tracks document revision history.
Add more documents in the same way.

#### Permissions
Cloudant lets you set permissions for an individual database. If you share this database with users, then
they will be able to access the database from their dashboard.
Generate an API key to provide credentials for programmatic access to a database.
You can perform basic create-read-update-delete operations on documents by directly referencing the
document ID.

#### Primary Key
Additionally, Cloudant creates the primary index for every database out-of-the-box and stores it in a btree
data structure. Cloudant uses the document ID as the primary key. The primary index is most useful
when you can find documents based on their ID.

Cloudant builds a secondary index using MapReduce, and stores it in a b-tree data structure, also. The
secondary index is useful when you need to analyze data or get a range of keys. For example, to count
data fields, sum or average numeric results, gather advanced statistics, and group by date.
The search index is built using Lucene search which is a unique feature of Cloudant. The search index is
useful to perform ad-hoc queries, find documents based on their contents, or work with groups, facets, or
geographies.

The Geospatial index is also unique to Cloudant and is stored in an r-tree data structure. The geospatial
index is most useful for complex geometries, advanced relations, and GeoJSON.
Cloudant Query uses “mongo-style” querying and is useful for ad-hoc queries, when using many logical
operators, or if you are familiar with querying data using MongoDB or SQL.

The Cloudant web site includes examples and tutorials for each type of index to help you get started. If
you sign in, then you will be able to add any of the sample databases to your Cloudant account.
This process uses the replication API under the covers to replicate the selected sample database to your
dashboard. You can create as many databases as you need in your account – each with any number of
documents.

The next time you load your dashboard, you’ll see the animaldb sample database in your list of databases.
The animaldb database includes a design document defining any secondary indexes that the database
should have. And the rest of the documents contain the information for each animal.
Cloudant leverages an HTTP API with the API URL giving you direct programmatic access from an
application or from the command line with the cURL utility. From here, you can also view the JSON
document at the specified URL.

The Cloudant HTTP API follows this hierarchical model.
* Account
* Database
* Document
* Attachment

A URL for the Cloudant API is made up of an account name, the database within that account, and the
endpoints to manipulate data within that database.

This example references the ablanks account, the employee_directory database, and for all documents in
the database, show the document body. You could use this programmatically to populate a web page that
shows all employees.

You make HTTP requests using these verbs:
* GET
* PUT
* POST
* DELETE
* COPY

Typically, when you access the data from a browser, you perform a GET; however, you can use browser
add-on tools or a command line tool to PUT, POST, DELETE, or COPY data.
You can use the API to perform all of these requests:
* Insert data
* Read data
* Create indexes
* Make queries
* Monitor the database
* Create replication jobs Or Create databases
 
Here’s what an HTTP API command looks like.
The first part indicates that this is an HTTP request.
Next, include a verb such as GET or PUT.

You can include headers, data that you are passing, then the URI and any parameters.
This cURL example executes a GET, passes the user credentials, and includes the base URI to access.
To start, it’s important to have a set of useful tools installed on your environment for accessing the

Cloudant HTTP API.
==================================

***cURL*** is a readily-available command line tool. You can use a Linux shell to issue cURL commands. 
Many Linux distributions have ***cURL*** preinstalled, so it’s best check your environment before installing this utility.
/jq is a useful ***cURL*** add-on tool for manipulating the JSON response from the Cloudant HTTP API so it is
formatted in a more readable way.

#### JSONView
Given that the API is HTTP, you can also access it directly from your browser. JSONView is a useful plug-in
for formatting the JSON response, equivalent to jq for ***cURL***. JSONView is great tool for both FireFox and
Chrome browsers. Instead of seeing raw JSON text, JSONView formats the JSON text to make it more
readable.

***RESTClient*** and ***POSTMan*** provide an easy user interface to manipulate the API, such as sending requests
to the Cloudant database, parsing a response, specifying a URL with credentials to authenticate, or adding
headers. This screen shows POSTMan in Chrome, but RESTClient in FireFox works similarly and are both
great tools for those who prefer to use a browser over a command line.

And if you prefer a visual experience, the Cloudant Dashboard provides an intuitive user interface for the
majority of the API functionality.


