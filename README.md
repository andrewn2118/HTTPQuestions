## HTTP Questions

__URLs__

* Name all of the parts of the url that you can remember.  In your own words describe what they do.

```
Protocol: either http:// or https:// which is a secure 
Domain: the address of the server
Port: added after the domain; default ports: http:// 80 - https:// 443
Path: after the port and before the query string; denotes the 
Query string: starts with ? and are arguments added to the url to modify the request
Anchor tag: starts with # and identifies a location or anchor on the page
```

* Name the pieces of the following urls:
	* `https://www.google.com/`

	```
	Protocol: https://
	Domain: www.google.com/
	```

	* `https://workbook.galvanize.com/cohorts/41/learning_experiences/367`
	
	```
	Protocol: https://
	Sub-domain: workbook
	Domain: galvanize.com/
	Path: /cohorts/41/learning_experience/367
	```

	* `http://locahost:5000/animals/puppies?onlycute=1&size=medium#firstpuppy`

	```
	Protocol: http://
	Domain: localhost:5000/
	Path: /animals/puppies
	Query string: ?onlycute=1&size=medium#firstpuppy
	```

	* `https://en.wikipedia.org/wiki/List_of_HTTP_status_codes#4xx_Client_Error`

	```
	Protocol: https://
	Sub-domain: en
	Domain:en. wikipedia.org/
	Path: /wiki/List_of_HTTP_status_codes
	Anchor tag: #4xz_Client_Error
	```

	* Can a server use more than 1 port?

	```
	Yes
	```

	* Why is https different than http?

	```
	https is secure and scrambles the code so only the server and client can decipher the code		
	```

	* How does a server interpret the following url's query paramter.  What data structure does it create on the server? `http://locahost:5000/animals?puppies=fido&puppies=max&puppies=moxie`

	```
	The server would create a puppies array ["fido", "max", "moxie"]
	```

__HTTP Request/Response__

* Name at least 4 http verbs

```
GET, POST, PUT, DELETE
```

* What is each verb useful for in your own words

```
GET: requests data from the server
POST: adds new data to the server
PUT: alters data on the server
DELETE: removes data from the server
```

* What does idempotent mean?

```
The operation on the server does not change its data
```

* Name the 5 http status code ranges.  What are they used for in general?

```
1xx: the requested process is still running and not yet finished
2xx: the request was processed
3xx: the request was redirected to another location
4xx: there was an error in the request on the client side
5xx: there was an error in the request on the server side
```

* If a server returns a http status code of 301 and a location of `https://www.google.com/`, what does the browser do?

```
The request was redirected to Google
```

* For the following HTTP headers, decide if the following header is used for requests, responses or both:
	* Accept
	
	```
	Request
	```
	
	* Content-type
		
	```
	Both
	```
	
	* User-agent
		
	```
	Request
	```
	
	* Set-cookies
		
	```
	Response
	```
	
	* Cache-control
		
	```
	Both
	```
	
	* Cookie
		
	```
	Request
	```

* Is the following a http request or response?  How do you know for each?

```
HTTP/1.1 200 OK
Access-Control-Allow-Origin: *
Vary: Accept
Content-Type: text/html; charset=utf-8
Content-Length: 722
ETag: W/"2d2-Wu0We9N5g35FXWY+gOATLA"
Date: Tue, 08 Mar 2016 20:37:11 GMT
Connection: keep-alive

<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <link rel="stylesheet" href="/style.css">
    <title>Student Roster</title>
  </head>
  <body>
    <main>
      <h1>Student Roster</h1>
      
        <section>
          <h3>Daenerys Targaryen</h3>
          <span>Student Id: nys8fbohl</span>
          <h4>Hobby: Motherhood</h4>
          <img src="https://i.imgur.com/KlycRG5.jpg" alt="Daenerys Targaryen" />
        </section>
      
        <section>
          <h3>Tyrion Lannister</h3>
          <span>Student Id: njehukbohe</span>
          <h4>Hobby: Traveling</h4>
          <img src="https://i.imgur.com/fFMusdC.png" alt="Tyrion Lannister" />
        </section>
      
    </main>
  </body>
</html>

	* Answer: Response (status code)
```

```
DELETE /students/n1vmyrw3x HTTP/1.1
Host: g22-students.herokuapp.com
Accept: application/json
Cache-Control: no-cache
Postman-Token: 0041e3c3-efdb-f0c3-b2f4-2d79f6d0f44b

	* Answer: Request (DELETE)
```

__JSON__

* Describe what JSON is.  What is it used for.

```
JSON = JavaScript Object Notation and is used for data transfer
```

* Convert the following map into a javascript object then console log the age.

```
{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software"}

Answer: 
console.log(JSON.parse('{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software"}').age);
```
* Convert the following to a javascript object.  Console log each company name.

```
{ "Companies":[ { "company": "Github", "age": 7, "categories": "Services,Internet,Software"},
              { "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"},
              { "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"},
              { "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}
            ]
}

Answer: 
JSON.parse('{ "Companies":[ { "company": "Github", "age": 7, "categories": "Services,Internet,Software"}, { "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"}, { "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"}, { "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"} ] }').Companies.forEach(function(el){ console.log(Companies.company) });
```
* The following is javascript.  Convert the object to a string and console log it.

```
var myObj = {
  company: "Galvanize",
  age: 3,
  categories: "Education"
};

Answer:
console.log(JSON.stringify(myObj));
```
__MISC__

* Describe what DNS is.

```
DNS = Domain Name System is a set of servers which looks up IP addresses and converts them to domain names
``` 

* In the terminal, type `man curl`.  Look at the man page for curl.  What do the following flags do? `-v`, `-X`.  (Hint: to search for a string, type `/` then the text you want, then enter.  To quit the man page, type `q`).

```
-v = -Verbose returns the request and response

-X = --request allows for adding a specific request method
```

* What is TCP/IP?  How does it interact with HTTP?

```
HTTP uses TCP/IP to send and receive data.

TCP = Transmission Control Protocol
TCP breaks the data down to packets and ensures the data is sent to the correct location and reassembles the data to ensure it remains the same. If data failes to send, TCP will resend the data.

IP = Internet Protocol
IP connects the client to the server
```

* Does HTTP break the data that is being sent into small packets?  If not, what protocol is responsible for it?

```
TCP handles breaking data down into packets
```

