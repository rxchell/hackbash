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
- 



