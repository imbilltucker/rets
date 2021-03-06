# RETS Changelog

## 0.3.5
* Forcing dict and OrderdDict types when sending search_filters to the session.

## 0.3.4
* Allowing users to specify the xml format when initializing the session with `metadata_format`

## 0.3.3
* Minor bug fix

## 0.3.2
* Checking the RETS response code with the login parser as well.

## 0.3.1
* Bug fix for GET requests to RETS servers.
* Minor documentation update.

## 0.3.0
* Search method now returns a list instead of an iterator. This allows us to catch maxrows internally and automatically
make subsequent reqeusts with offsets rather than forcing the client to catch and adapt. As the size of the reply is often
 small, getting even ~32k listings of data was >300k in memory, this results should not affect the memory footprint.
* Added the `auto_offset` parameter for Session.search method. Defaults to True for making subsequent search requests
if the RETS server truncated the number of requested listings.

## 0.2.0
* Significatn changes to exception raising. No more InvalidFormat exception. ValueErrors are more appropriate for
input errors and RETSExceptions for consistently handling non-zero reply codes from the RETS Server. The RETSException
now has reply_code and reply_text parameters. 

## 0.1.3
* get_object requests with location=1 now parse the response appropriately

## 0.1.2
* getObject dictionaries now include md5 fingerprints as content_md5

## 0.1.1
* Multipart image downloads working in Python2. Still not working in Python3

## 0.1.0
* No results continues generator

## 0.0.12
* Action capability called correctly
* RETS Version no longer strips RETS/ prematurely
* Added additional INVALID_VERSION reply code for cathing STANDARD_XML
* Minor Bug Fixes

## 0.0.8 
* Removing lxml from requirements
* Parsing STANDARD-XML
* Removing need to manage RETS version
* User Agent Auth

## 0.0.7
* Streaming search results
