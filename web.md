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


# Cross-site scripting (XSS) 

## Cookies 
- how would you design a system where multiple webpages need authentication with a common set of credentials?
- information sent by browser to server, and server will send the info related to the site
- `setCookies` header
- once issued with a cookie, the browser will send whatever request you make with the server
- if someone takes your cookies, someone can use your identity 

1. HTTP request from client (browser) to server (website)
2. HTTP response + **Set-Cookies** from server to client
3. HTTP request + **Cookies (SessionID)** from client to server
4. HTTP response from server to client 

## Making HTTP requests in JavaScript
- **Fetch API** (old way: xml http requests) for JavaScript to pull information from websites to dynamically update a page
``` JavaScript
response = awaits fetch("/secret");  // background request to get secret page and store in response. (successful authentication + send cookies --> fetch is possible) 
text = await response.text();        // get response text 
console.log(text);
```

```JavaScript
fetch("https://gmail.com")
```
- Not possible
  
## Same origin (scheme + host + port) policy 
- webpages only permitted to access data from other sources if they have the same origin 
- eg https + google.com + 403
- allows attacker to introduce malicious JavaScript within the same origin
- 
- **webhook.site** gives you an URL to infiltrate

## Prevent cross-site scripting 
- fliter user input when it arrives at the server. reject anything that does not conform to expected input
- encode data (eg HTML encoding[https://emn178.github.io/online-tools/html_encode.html], JavaScript encoding) on output, so browser knows which part of html to not execute. using wrong encoding scheme for the context can lead to bypasses 
- set sensitive cookies to HttpOnly so they are not accessible directly by JavaScript. prevents stealing the cookie directly, but still lets attackers do what they want as the user under the origin
- Content Security Policy (http header in http response): tell the browser that browser should only execute certain scripts (eg loaded remotely from particular domains / follow particular format / have particular content)
- 





