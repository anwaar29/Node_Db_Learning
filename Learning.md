# DAY 1-  
#  Introduction to Node JS

Node.js is a server-side JavaScript runtime built on the Chrome V8 JavaScript engine. It allows developers to build scalable, event-driven applications using JavaScript both on the front-end and back-end of web development.

Traditionally, JavaScript has been used primarily on the client side of web development, running in the user's web browser to manipulate the Document Object Model (DOM) and create interactive web pages. However, with Node.js, developers can now use JavaScript to build server-side applications that run outside of the user's browser, such as web servers, API servers, and command-line tool
Node.js also has a large ecosystem of packages and modules available through its package manager, npm, which make it easy to add additional functionality to your applications. This has made it a popular choice for building web applications, especially those that require real-time data updates or highly-scalable architectures.

# Features of Node.js/Why We use

Node.js is an open-source server-side JavaScript runtime environment that allows developers to build scalable and high-performance applications. Some of the features of Node.js include:
 Asynchronous Programming Model: Node.js is designed to handle large-scale, high-traffic applications with a non-blocking, event-driven I/O model. It allows developers to write asynchronous code that can handle many requests simultaneously without blocking other requests.

Cross-platform Compatibility: Node.js is a cross-platform runtime environment that can run on various platforms, including Windows, macOS, and Linux.
Fast Performance: Node.js uses Google's V8 JavaScript engine to compile JavaScript code, resulting in high-performance applications. It also has a lightweight runtime that reduces memory usage and makes it faster.

NPM: Node.js comes with an extensive package manager called NPM, which has over 1 million modules available for use. Developers can easily download and use packages to add new functionality to their applications.
 Real-time Web Applications: Node.js is ideal for building real-time applications like chat applications, gaming applications, and social media applications. It uses WebSockets to enable real-time communication between clients and servers.

 Scalability: Node.js is highly scalable and can handle a large number of concurrent connections. It allows developers to create highly scalable applications that can handle thousands of simultaneous connections with ease.
   
 Easy to Learn: Node.js is easy to learn for developers who have experience with JavaScript. It uses the same language for both the client and server-side, which makes it easy to maintain and develop applications.

#   Node.JS V/S Browser

Node.js and web browsers are two different environments with different purposes and functionalities. Here are some key differences:

Execution Environment: Node.js is a server-side JavaScript runtime environment, whereas web browsers are client-side environments used to render web pages.

Modules and Libraries: Node.js has a vast ecosystem of modules and libraries that allow developers to build complex applications quickly. Browsers have their own set of APIs that allow developers to create web applications.

Node.js is used for server-side development, while browsers are used for client-side development. However, both environments use JavaScript as the primary language and have their own set of APIs and functionalities.
   
# Module. Exports

In Node.js, module.exports is a special object that is used to expose functions, objects, or values from a module to other parts of an application.

Every JavaScript file in Node.js is treated as a module, and by default, the variables, functions, and objects defined in a module are scoped only to that module. However, if we want to use those variables, functions, or objects in other modules, we need to export them using module.exports.

```
//greeting.js
                             function sayHello(name) {
                             console.log(`Hello, ${name}!`);
                                                                      }
                               module.exports = sayHello;

```
In this example, the sayHello function is defined in the greeting.js module and is exported using the module. exports. This means that other modules can now require this module and use the sayHello function:
```
 const sayHello = require('./greeting');

                          sayHello('John'); // prints "Hello, John!"

```
In this example, the sayHello function is imported into the index.js            
module using the require() function, which returns the exported function from the greeting.js module.

# // Another way of exporting Names Export

```
// greeting.js
                                                  exports.sayHello = function(name) {
                                                            console.log(`Hello, ${name}!`);
                                                                                                          };

                                                      exports.sayGoodbye = function(name) {
                                                       console.log(`Goodbye, ${name}!`);
                                                                                                              };
```
In this example, we export two functions (sayHello and sayGoodbye) from the greeting.js module using named exports. We can then import these functions in another module like this:
```
// index.js
                                   const { sayHello, sayGoodbye } = require('./greeting');

                                   sayHello('John'); // prints "Hello, John!"
                               sayGoodbye('John'); // prints "Goodbye, John!"
```

In the above code, we are using the module as we did before but here this is names export so we have to put modules  inside {}

#      DAY 2

# Creating a NodeSimple  Server

```
 Node.js has a built-in module called HTTP, which allows Node.js to transfer data over the Hyper Text Transfer Protocol (HTTP). To include the HTTP module, use the 


                             require() method: 
                           var http = require('http');
                    const http = require('http');

                            const server = http.createServer((req, res) => {
                               res.write(‘anwaar);
                               res.end();
});

server.listen(3000, () => {
  console.log('Server started on port 3000');
});

```
This is the example of the simple HTTP server and in the last we are giving a port number to you server on which your server will run and also im passing a callback function and gave a msg in the console  so whenever  we execute our code this callback function will run and give you a message in your console

# Handle HTTP Request
The http.createServer() method includes request and response parameters which is supplied by Node.js. The request object can be used to get information about the current HTTP request e.g., url, request header, and data. The response object can be used to send a response for a current HTTP request.
```
var http = require('http'); // Import Node.js core module

var server = http.createServer(function (req, res) {   //create web server
    if (req.url == '/') { //check the URL of the current request
        
        // set response header
        res.writeHead(200, { 'Content-Type': 'text/html' }); 
        
        // set response content    
        res.write('<html><body><p>This is home Page.</p></body></html>');
        res.end();
    
    }
    else if (req.url == "/student") {
        
        res.writeHead(200, { 'Content-Type': 'text/html' });
        res.write('<html><body><p>This is student Page.</p></body></html>');
        res.end();
    
    }
    else if (req.url == "/admin") {
        
        res.writeHead(200, { 'Content-Type': 'text/html' });
        res.write('<html><body><p>This is admin Page.</p></body></html>');
        res.end();
    
    }
    else
        res.end('Invalid Request!');

});

server.listen(5000); //6 - listen for any incoming requests

console.log('Node.js web server at port 5000 is running..')
```
In the above example, req.url is used to check the url of the current request and based on that it sends the response. To send a response, first it sets the response header using writeHead() method and then writes a string as a response body using write() method. Finally, Node.js web server sends the response using end() method.

# Express Overview

## Express is a minimal and flexible Node.js web application framework that provides a robust set of features to develop web and mobile applications. It facilitates the rapid development of Node based Web applications. Following are some of the core features of Express framework −
 ## Allows to set up middlewares to respond to HTTP Requests.
## Defines a routing table which is used to perform different actions based on HTTP Method and URL.
##  Allows to dynamically render HTML Pages based on passing arguments to templates.

# Installing Express
```
, install the Express framework globally using NPM so that it can be used to create a web application using node terminal.
 $ npm install express --save

```
# Why Express JS?

Express was created to make APIs and web applications with ease,
It saves a lot of coding time almost by half and still makes web and 
mobile applications are efficient.
Another reason for using express is that it is written in javascript as javascript is an easy language even if you don't have a previous
knowledge of any language. Express lets so many new developers enter the field of web development.
The reason behind creating an express framework for node js is:

Time-efficient

Fast

Economical

Easy to learn


Asynchronous

# Request & Response

```
Express application uses a callback function whose parameters are request and response objects.
app.get('/', function (req, res) {
      // --
})

Request Object − The request object represents the HTTP request and has properties for the request query string, parameters, body, HTTP headers, and so on.
Response Object − The response object represents the HTTP response that an Express app sends when it gets an HTTP request

```

# example

```
var express = require('express');
var app = express();

app.get('/', function (req, res) {
   res.send('Hello World');
})

var server = app.listen(8081, function () {
     
   console.log(‘sever is running)
})

```
# Basic Routing

We have seen a basic application which serves HTTP request for the homepage. Routing refers to determining how an application responds to a client request to a particular endpoint, which is a URI (or path) and a specific HTTP request method (GET, POST, and so on).

We will extend our Hello World program to handle more types of HTTP requests.
```
var express = require('express');
var app = express();

// This responds with "Hello World" on the homepage
app.get('/', function (req, res) {
   console.log("Got a GET request for the homepage");
   res.send('Hello GET');
})

// This responds a POST request for the homepage
app.post('/', function (req, res) {
   console.log("Got a POST request for the homepage");
   res.send('Hello POST');
})

// This responds a DELETE request for the /del_user page.
app.delete('/del_user', function (req, res) {
   console.log("Got a DELETE request for /del_user");
   res.send('Hello DELETE');
})

// This responds a GET request for the /list_user page.
app.get('/list_user', function (req, res) {
   console.log("Got a GET request for /list_user");
   res.send('Page Listing');
})

// This responds a GET request for abcd, abxcd, ab123cd, and so on
app.get('/ab*cd', function(req, res) {   
   console.log("Got a GET request for /ab*cd");
   res.send('Page Pattern Match');
})

var server = app.listen(8081, function () {
   var host = server.address().address
   var port = server.address().port
   
   console.log("Example app listening at http://%s:%s", host, port)
})

```

# DAY 3


# Different kinds of HTTP requests

GET: GET request is used to read/retrieve data from a web server. GET returns an HTTP status code of 200 (OK) if the data is successfully retrieved from the server.

POST: POST request is used to send data (file, form data, etc.) to the server. On successful creation, it returns an HTTP status code of 201.

PUT: A PUT request is used to modify the data on the server. It replaces the entire content at a particular location with data that is passed in the body payload. If there are no resources that match the request, it will generate one.

PATCH: PATCH is similar to PUT request, but the only difference is, it modifies a part of the data. It will only replace the content that you want to update.

DELETE: A DELETE request is used to delete the data on the server at a specified location.


# Middleware in Node.JS

#### Middleware Node.JS is a function that plays a vital role in the request-response lifecycle of Node.JS execution. Using middleware functions, you can run any code and easily change response and request objects. Not only that, you can end the request-response lifecycle if you want and run the following middleware function using the next function. This blog delves deep into middleware, its importance, middleware in Node.JS, its types, and many others.

![n1](https://user-images.githubusercontent.com/97968236/221568430-672644dd-968e-4019-bdcb-4aee5d758dea.png)

# Advantages of using middleware:

Middleware can process request objects multiple times before the server works for that request.
Middleware can be used to add logging and authentication functionality.
Middleware improves client-side rendering performance.
Middleware is used for setting some specific HTTP headers.
Middleware helps for Optimization and better performance.

# Middleware Chaining:  
  
  Middleware can be chained from one to another, Hence creating a chain of functions that are executed in order. The last function sends the response back to the browser. So, before sending the response back to the browser the different middleware process the request.

  The next() function in the express is responsible for calling the next middleware function if there is one .
  
  # Modified requests will be available to each middleware via the next function –


  

#![n2](https://user-images.githubusercontent.com/97968236/221569967-7fddbc7b-4b04-4ecf-973d-ca393df00eec.png)

```
const express = require('express')
const app = express()

const myLogger = function (req, res, next) {
  console.log('LOGGED')
  next()
}

app.use(myLogger)

app.get('/', (req, res) => {
  res.send('Hello World!')
})

app.listen(3000)
```
Every time the app receives a request, it prints the message “LOGGED” to the terminal.

The order of middleware loading is important: middleware functions that are loaded first are also executed first.

If myLogger is loaded after the route to the root path, the request never reaches it and the app doesn’t print “LOGGED”, because the route handler of the root path terminates the request-response cycle.

The middleware function myLogger simply prints a message, then passes on the request to the next middleware function in the stack by calling the next() function.
