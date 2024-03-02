# HTTP request 

1. URL
- protocol: https
- domain name 
- port number
- path to resource: after /
- value of query parameter "num"
- anchor

2. Browser looks up IP address corresponding to the domain name using DNS
3. Establishes a connection to the web server using the IP address and web server
4. Make HTTP request
- HTTP method: GET or POST
- Path to resource and parameters

## Request method 
### GET
- retrieves the resource
- pulling information from database
- entering the URL on the browser should not modify (eg delete, add data) contents on the server 

### POST
- sends data (eg name of file, json xml) to the resource for the server to do something with 
- include data to be sent

### other methods 
- PUT
- DELETER
- HEAD
- etc

## HTTP Headers
- allows client and server to define additional info about HTTP request / response

- host: identifies domain and port where the request is being sent 
- content-length: size of message body in bytes, so that server knows when to stop processing the request 
- referer[sic]: identifies webpage that requested the resource 
- user-agent: identifies the client software (e.g Chrome, Firefox) that made the request 
- cookie: any cookies the client has that are associated with the server

## Over to the server 
- server receives HTTP request, parses it

## Retrieving data
- can be stored on file system or database
- types: relational, document-oriented, graph etc
- language to query relational databases: Structured Query Language (SQL)
- different tables linked together by common data

## Presenting data
- after the data is retrieved, it needs to be assembled into a format the browser can display
- HTML (tags, attributes, content)
- HTML by itself is static. cannot dynamically make things appear and disappear, change info real-time. (eg have to click to get to the next page instead of the page changing real-time as you type eg in the search bar)

## JavaScript
- scripting language to augment webpages with dynamic behaviour
- can be included within HTML or from an external source
```JavaScript
<script src="/path/to/script.js"></script> // run script from external URL on the page 
```

## Delivering the response 
- send the response to the client (browser)
- status code to indicate if it is successful: `HTTP/1.1 200 OK`
- response headers
- response body

### HTTP status codes
- 200 OK

codes begin with 4: client's fault 
- 404 Not Found
- 403 Forbidden (no permission to access)
- 400 Bad Request (incorrect way of making the request)

codes begin with 5: server's end, eg programming error, script not working properly, cannot conenct to databse 
- 500 Internal Server Error 

## Back to the browser 
- browser receives HTML and parses it
- renders page based on http

## Play with HTTP requests using Burp Suite




