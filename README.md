## HTTP Questions

__URLs__

* Name all of the parts of the url that you can remember.  In your own words describe what they do.

//Answers:

1. Protocol: The way in which browsers, servers and other programs make request from each other.
2. Domain: Is the human readable version of the ip address.
3. Port: the entrance/exit of your computer to the web.
4. Path: is the file path--page your reaching.
5. query string: Are parameters passed to the URL to make the request more specific.
6. anchors: Are within page links--allow you to link one part of the page to another.

Name the pieces of the following urls:

* `https://www.google.com/`
	
```	
Answer: https is the secure protocol followed by the google Domain.
```	
* `https://workbook.galvanize.com/cohorts/41/learning_experiences/367`
		
```
Answer:	secure protocol, followed by the Domain and then path after .com/
```	
* `http://locahost:5000/animals/puppies?onlycute=1&size=medium#firstpuppy`
		
```
Answer: The protocol, followed by the port, then the path and then the  querystring after the question mark
```	
* `https://en.wikipedia.org/wiki/List_of_HTTP_status_codes#4xx_Client_Error`
	
```
Answer: The secure protocol, followed by the Domain and then the path
```
* `Can a server use more than 1 port?`

``` 
Answer: Yes
```  
* `Why is https different than http`
		
```
Answer: 's' signifies secure the communication is encoded between the server and client
```
* `How does a server interpret the following url's query paramter.  What data structure does it create on the server?`

 `http://locahost:5000/animals?puppies=fido&puppies=max&puppies=moxie`

```
Answer:The server interprets this as an array of puppies with the values fido, max and moxie
```

__HTTP Request/Response__

* Name at least 4 http verbs

```
Answer: GET, POST, PUT, DELETE
```

* What is each verb useful for in your own words

```
Answer: GET:making request, POST:submitting new data, DELETE: removing data, PUT: updating data
```

* What does idempotent mean?

```
Answer: An operation that after being opertating on some data doesn't change in value of that data.
```

* Name the 5 http status code ranges.  What are they used for in general?

```
Answer: 200 = Coo aka OK , 300 = Go that way aka redirect, 400 = you effed up aka Client, 500 = I effed up aka Server
```

* If a server returns a http status code of 301 and a location of `https://www.google.com/`, what does the browser do?

```
Answer: The browswer redirects to some other page typically with some more information about why you were redirected and some other options 
```

* For the following HTTP headers, decide if the following header is used for requests, responses or both:
	* Accept
	* Content-type
	* User-agent
	* Set-cookies
	* Cache-control
	* Cookie
	
```
Answer: Accept: requests, Content-type: responses, User-agent: requests, set-cookies: responses, Cookie: requests
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
```

```
DELETE /students/n1vmyrw3x HTTP/1.1
Host: g22-students.herokuapp.com
Accept: application/json
Cache-Control: no-cache
Postman-Token: 0041e3c3-efdb-f0c3-b2f4-2d79f6d0f44b
```
```
Answer: The first is a response, because it starts with a status code and latter is a request because its starts with a HTTP verb
```

__JSON__

* Describe what JSON is.  What is it used for.

```
Answer: Data exchange for the web that resembles a JS object, but is a string that can be parsed to into JS for manipulation.
```

* Convert the following map into a javascript object then console log the age.

```
{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software"}
```

```
Answer: var jsObj = JSON.parse("{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software"}");

console.log(jsObj.age);
```
* Convert the following to a javascript object.  Console log each company name.

```
{ "Companies":[ { "company": "Github", "age": 7, "categories": "Services,Internet,Software"},
              { "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"},
              { "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"},
              { "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}
            ]
}
```
```
Answer: var jsObj = JSON.parse('{ "Companies":[ { "company": "Github", "age": 7, "categories": "Services,Internet,Software"},{ "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"},{ "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"},{ "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}]}');

jsObj.Companies.map(function(company){
     console.log(company.company);
});
```
* The following is javascript.  Convert the object to a string and console log it.

```
var myObj = {
  company: "Galvanize",
  age: 3,
  categories: "Education"
};
```
```
Answer: var json = JSON.stringify(myObj);
console.log(json);
```
__MISC__

* Describe what DNS is.

```
Answer: Domain name system: Is a system to translate domain names into ip addresses to find content on the web. After we type the address in dthe url a set a queries starting with the browser, then OS then Resolving Name Server, then the Root Name Server, then the TLD Name Server, then the Authoritative Name Server.
```

* In the terminal, type `man curl`.  Look at the man page for curl.  What do the following flags do? `-v`, `-X`.  (Hint: to search for a string, type `/` then the text you want, then enter.  To quit the man page, type `q`).

```
Answer: -v: short for version--to see if your  curl  supports  GSS-API/SSPI  and SPNEGO, -X: allows the user to use their email's unique identifier rather than message id for request
```

* What is TCP/IP?  How does it interact with HTTP?

```
Answer: TCP/IP: Transmission Control Protocol/Internet Protocol (address) - TCP establishes the connection between the two hosts and exchange of streams of data. TCP guarantees that packets are delivered in the same order in which they were sent. IP is used by TCP and deals with the  packets. And HTTP utilizes them both while also handling the clients request and server responses. 
```

* Does HTTP break the data that is being sent into small packets?  If not, what protocol is responsible for it?

```
Answer: No, IP deals with the packets and TCP guarentees the arrive in the same order they were sent.
```

