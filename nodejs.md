1. [NodeJS Introduction](#nodejs)
	* [What is nodejs](#what-is-nodejs)
  	* [What is v8](#what-is-v8)
  	* [What nodejs is not](#what-nodejs-is-not)
  	* [Who has developed nodejs](#who-has-developed-nodejs)
	* [Why nodejs](#why-nodejs)
	* [What are the limitations of nodejs](#what-are-the-limitations-of-nodejs)
	* [Installation](#installation)
	* [What is REPL](#what-is-repl)
	* [What is npm](#what-is-npm)
	* [How nodejs work](#how-nodejs-work)
	* [Explain nodejs architecture](#explain-nodejs-architecture)
	* [Who are using nodejs for their development](#who-are-using-nodejs-for-their-development)
	* [What is event loop](#what-is-event-loop)
	* [What is callback](#what-is-callback)
	* [What is callback hell](#what-is-callback-hell)
	* [How to avoid callback hell](#how-to-avoid-callback-hell)
	* [What Are Buffer](#what-are-buffer)
	* [What are Streams](#what-are-streams)
	* [What are evets and event emitters](#what-are-evets-and-event-emitters)
	* [How to create HTTP server using nodejs](#how-to-create-http-server-using-nodejs)
	* [What are nodejs HTTP module limitations](#what-are-nodejs-http-module-limitations)
	* [What are middlewares in nodejs](#what-are-middlewares-in-nodejs)
	* [What is the difference between exports and module.exports](#what-is-the-difference-between-exports-and-module.exports)
2. [NodeJS Questions And Answers](#nodejs-questions-and-answers) 
3. [NodeJS Pupular Modules](#nodejs-pupular-modules)
	* [express](#express)
   		* [cookie-parser](#cookie-parser)
   		* [body-parser](#body-parser)
   		* [async](#async)
   		* [socket.io](#socketio)
    	* [engine.IO](#engineio)
   		* [passport](#passport)   
   		* [nodemailer](#nodemailer)
   		* [mysql](#mysql)
   		* [mongodb](#mongodb)
    	* [mongoose](#mongoose)
   		* [lodash](#Lodash)
   		* [request](#request)
   		* [chalk](#chalk)
   		* [bluebird](#bluebird)
    	* [commander](#commander)
   		* [moment](#moment)
   		* [fs](#fs)
   		* [q](#q)
    	* [winston](#winston)
   		* [swagger](#swagger)
   		* [redis](#redis)
   		* [handlebars](#handlebars)
   		* [ejs](#ejs)
    	* [dotenv](#dotenv)
   		* [jsonwebtoken](#jsonwebtoken)
   		* [cors](#cors)
  	

# NodeJS

## Introduction

### What is nodejs?
Node.js is a javascript runtime built on chrome’s V8 engine for building fast scalable network application. Node.js uses an event driven, non-blocking I/O model that makes it lightweight and efficient. 

Node.js is basically a library and a runtime environment that allows us to execute javascript on the server.

### What is V8?

V8 is Google’s open-source high-performance javascript engine written in c++ and implements ES5.

**Key Points about V8 JavaScript Engine:**

* It can be run standalone or can be embedded into any C++ application.
* It uses just-in-time compilation (JIT) to execute JavaScript code.
* It is used by many open source projects like Node.js and MongoDB to execute JavaScript on server side.
* Compiles and executes javascript source code.
* Handles memory allocation for objects.
* Garbage collects the objects if no longer needed.

**Virtual machines used by different browsers:**

* **v8** used by `Google`
* **Chakra** used by `MicroSoft`
* **SpiderMonkey** used by `Mozzila`
* **JavaScriptCore** used by `Apple`

### What Node.js is not?
* Node.js is not a JavaScript library, but it is a platform to execute JavaScript on server side.
* Node.js programs are written in JavaScript but there is no DOM manipulation provided by Node.js.

### Who has developed Node.js?
Node.js was developed by `Ryan Dahl` and other developers working at `Joyent`. It was first released in 2009
supporting only Linux. In 2011, windows version was released.

### Why Node.js?
**Open Source:** Node.js is open source, so it’s free to use and no need to pay for license. There are also many open
source modules supported by Node.js.

**No need to learn another language for server side code.**

**Non-blocking**

**Very Fast**

**Single threaded but highly scalable:** You can scale your Node.js application by using two ways – `Horizontal Scaling` and `Vertical Scaling`,
which helps you to improve your application performance.

* In Horizontal scaling you can add more nodes to your existing system.
* In Vertical scaling you can add more resources to a single node.

### What are the limitations of Node.js?
There are following limitations of Node.js:

* It doesn’t support multi-threaded programming.
* It doesn’t support very high computational intensive tasks. When it executes long running task, it will queue
all the incoming requests to wait for execution, since it follows JavaScript event loop which is single
threaded.
* Node is not good for executing synchronous and CPU intensive tasks.

## Installation

### Ubuntu:
**Supported Ubuntu versions:**

* Ubuntu 14.04 LTS (Trusty Tahr)
* Ubuntu 16.04 LTS (Xenial Xerus)

**Install stable version:**
```
$ curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
$ sudo apt-get install -y nodejs
$ nodejs -v
```
**Install latest version:**
```
$ curl -sL https://deb.nodesource.com/setup_9.x | sudo -E bash -
$ sudo apt-get install -y nodejs
$ nodejs -v
```

**Optional:** install build tools

To compile and install native addons from npm you may also need to install build tools:

`$ sudo apt-get install -y build-essential`

### what is REPL?
Node.js comes with virtual environment called REPL(Node shell). REPL stands for Read-Eval-Print-Loop. It is an interface to run your JavaScript code and see the results..

You can test pretty much any Node.js/JavaScript expression in REPL. For example, if your write `10 + 20` then it will display result `30` immediately in new line.

**Read-Eval-Print-Loop:**

**Read** − Reads user's input, parses the input into JavaScript data-structure, and stores in memory.

**Eval** − Takes and evaluates the data structure.

**Print** − Prints the result.

**Loop** − Loops the above command until the user presses ctrl-c twice.

The REPL feature of Node is very useful in experimenting with Node.js codes and to debug JavaScript codes.

### What is npm?
Npm stands for node package manager. It has main 2 functions.

* Online repositories for Node.js package/modules
* Command line utility to install Node.js modules, version management and dependency management.

You can check easily whether NPM ins installed or not. 

`$ npm --version` 

Or 

`$ npm -v`

Both will display NPM version installed on your system.
See Image:

![NPM Version](https://github.com/hotam-singh/tutorials/blob/master/images/node9.png)

#### Install Modules Using NPM

`$ npm install <module_name>`

**Example:**

`$ npm install express`

#### Install Modules Listed in Package.json

`$ npm install`

It will install all modules present in `package.json` file

#### Uninstall a Module

`$ npm uninstall <module_name_to_be_uninstalled>`

#### Update a Module

`$ npm update <module_name_to_be_updated>`

### How Node.js work?

Traditional Web Server

![Traditional Web Server](https://drive.google.com/uc?export=view&id=1MvyKGX4mFJMFdXdhqc8mPWvj-95sEESp)

Node.js Process Model:

![NodeJS Process Model](https://github.com/hotam-singh/tutorials/blob/master/images/node_2.png)

### Explain Node.js Architecture?
Node.js has mainly two types of components – core components and node.js API (modules). The core
components are written in C and C++, and node.js API are written in JavaScript. Diagram for Node.js architecture
is given below:

![NodeJS Architecture](https://github.com/hotam-singh/tutorials/blob/master/images/node8.png)

**C/C++ Add-ons:** – You can also develop your Node.js Add-ons using C/C++ to work with Node.js.

**Node.js Binding:** – These are Core API, which bind the JavaScript with C / C++ libraries.

**Node.js API:** – These are written in JavaScript and directly exposed to outer world to interact with Node.js internal
components.

**V8:** – It is Google’s open source JavaScript engine, written in C++. Actually, it is a JavaScript VM which compile the
JavaScript code into native machine code instead interpretation. It is the fastest JIT (Just-In-Time) compiler for
JavaScript.

**Libuv:** – It is a multi-platform support C++ library which is responsible for handling thread pool, event loop and
async I/O operations in Node.js. In Node.js, blocking I/O operations are delegated to LibUV modules which has a
fixed size C++ thread pool to handle these operations. When these operations are completed, they are notified to
Event loop.

**C-ares:** – It is a C library for handling async DNS request, name resolves and multiple DNS queries in parallel.

**http_parser:** – It is a C library for parsing HTTP request and response.

**OpenSSL:** – It is a C library for the implementation of Secure Sockets Layer (SSL v2/v3) and Transport Layer Security
(TLS v1) protocols. It also provides all the necessary cryptography methods like hash, cipher, decipher, sign and
verify etc.

**Zlib:** – It is a C library for data compression and decompression.

### Who are using Node.js for their development?
Following companies are using Node.js for their development:

* Walmart
* E-bay
* PayPal
* Microsoft
* LinkedIn
* Yahoo
* Google
* SAP
* IBM
* Strong Loop
* Dropbox

### What is Event Loop. How it works?


Node.js is a single-threaded application, but it can support concurrency via the concept of event and callbacks. These events and callbacks are handled by event loop.
Event Loop: It has main 2 functionalities

* Whatever the task `Web APIs` hands over  to event loop, It simply adds them up in the `callback queue`.
* Looks if `call stack` is free, pick task from the callback queue and puts it into call stack for execution.

![Event Loop](https://github.com/hotam-singh/tutorials/blob/master/images/node_3.png)

#### Call Stack: 
Call Stack is only the javascript runtime on server where javascript is run.
#### Web APIs:
Web APIs are those handlers which makes async programming possible. Web APIs are basically callbacks that return response once completed the given task.

#### Callback Queue:
callback queue is a queue where all callbacks are queued up. Event loop process tasks from this queue.

### What is callback?
A callback is an anonimous function which passed as an argument to an asynchronous function, that describes what
to do after the asynchronous operation has completed. Callbacks are used frequently in node.js development.

```javascript
var fs = require('fs');
//callback function to read file data
fs.readFile('text.txt', 'utf8', function (err, data) { //callback function
	console.log(data);
});
```

### What is callback-hell?
Callback hell is a nested callbacks. It leads to some confusion and difficult-to-read code when nested callbacks are very deep.

**For Example:**
```javascript
    getData(function(a) {
        getMoreData(a, function(b) {
            getMoreData(b, function(c) {
                getMoreData(c, function(d) {
                    getMoreData(d, function(e) {
    					//And so on
    				});
    			});
    		});
    	});
    }); 
```

### How to avoid callback-hell?
We can avoid callback hell with the following methods: 

* Async/await (A NodeJS Library)
* Modularize the code `// Refactor the code in modules or separate functions`
* Promises

**Removing callback-hell with Async Module:**
```javascript
// It is a fast function
Function fastFunction() {
	setTimeout(function() {
		done();
	}, 100);
}

// It is slow function
Function slowtFunction() {
	setTimeout(function() {
		done();
	}, 300);
}

//Entry point
var async = require('async');  
async.waterFall([fastFunction, slowtFunction], function(err) {
	if(err) {
    	console.log('Error: ', err);
        return 
    }
	console.log('done');
});
```

**Removing callback-hell with promises:**
```javascript
var promise = require('es6-promise');

//Function to clean a room
var cleanRoom = function() {
	return new promise(function(resolve, reject) {
		resolve('cleaned the room');
	});
};

// Function to remove garbage
var removeGarbage = function() {
	return new promise(function(resolve, reject) {
		resolve('Garbage is removed');
	});
};

//Function to win Icecream
var winIcecream = function() {
	return new promise(function(resolve, reject) {
		resolve('I won icecream');
	});
};

// Async Flow control with promises
cleanRoom().then(function(data) {
	return removeGarbage();
}).then(function(data) {
	return winIcecream();
}).then(function(data) {
	console.log('finished');
});

//Callback will be returned once all tasks completed
promise.all([cleanRoom, removeGarbage, winIcecream]).then(function() {
	console.log('finished');
});

//Callback will be returned on every task completed
promise.race([cleanRoom, removeGarbage, winIcecream]).then(function() {
	console.log('one of the task finished');
});
```
### What Are Buffer?

**Official Definition:**

Buffer is a mechanism for reading or manipulating streams of binary data. Buffers are instances of the `Buffer` class in node, which is designed to handle raw binary data. Each buffer corresponds to some raw memory allocated outside V8. Buffers act somewhat like arrays of integers, but aren't resizable and have a whole bunch of methods specifically for binary data. In addition, the "integers" in a buffer each represent a byte and so are limited to values from 0 to 255 (2^8 - 1), inclusive.

**Typical example and definition:**

We know that a stream of data is the movement of data from one point to the other, but how exactly are they moved?

Typically, the movement of data is usually with the intention to process it, or read it, and make decisions based on it. But there is a minimum and a maximum amount of data a process could take over time. So if the rate the data arrives is faster than the rate the process consumes the data, the excess data need to wait somewhere for its turn to be processed.

On the other hand, if the process is consuming the data faster than it arrives, the few data that arrive earlier need to wait for a certain amount of data to arrive before being sent out for processing.

That **waiting area** is the `buffer!` It is a small physical location in your computer, usually in the RAM, where data are temporally gathered, wait, and are eventually sent out for processing during streaming.

We can think of the whole stream and buffer process as a bus station. In some bus stations, a bus is not allowed to depart until a certain amount of passengers arrive or until a specific departure time. Also, the passengers may arrive at different times with different speed. Neither the passengers nor the bus station has control over passengers’ arrival at the station.

In any case, passengers who arrive earlier will need to wait until the bus station decides to send the bus on its way. While passengers who arrive when the bus is already loading or when the bus has already departed need to wait for the next bus.

In whatever the case may be, there is always a waiting place. That is the Buffer to Node.js! Node.js can’t control the speed or time of data arrival, the speed of the stream. It only can decide when it’s time to send out the data. If it’s not yet time, Node.js will put them in the buffer — the **waiting area** — a small location in the RAM, until it’s time to send them out for processing.

A typical example where you could see buffer in action is when you’re streaming a video online. If your internet connection is fast enough, the speed of the stream will be fast enough to instantly fill up the buffer and send it out for processing, then fill another one, and send it out, then another, and yet another… till the stream is finished.

But if your connection is slow, after processing the first set of data that arrived, the video player will display a loading icon, or display the text “buffering”, which means gathering more data, or waiting for more data to arrive. And when the buffer is filled up and processed, the player shows the data, the video. While playing that, more data will continue to arrive and wait in the buffer.

#### Where You See Buffers:
In the wild, buffers are usually seen in the context of binary data coming from streams, such as `fs.createReadStream`.

#### Usage:
There are a few ways to create new buffers:
```
var buffer = new Buffer(8);
```
This buffer is uninitialized and contains 8 bytes.

```
var buffer = new Buffer([ 8, 6, 7, 5, 3, 0, 9]);
```
This initializes the buffer to the contents of this array. Keep in mind that the contents of the array are integers representing bytes.

```
var buffer = new Buffer("I'm a string!", "utf-8")
```
This initializes the buffer to a binary encoding of the first string as specified by the second argument (in this case, utf-8). utf-8 is by far the most common encoding used with node, but Buffer also supports:

* **ascii:** This encoding is way fast, but is limited to the ascii character set. Moreover, it will convert null characters into spaces, unlike the utf-8 encoding.
* **ucs2:** A two-byte, little-endian encoding. Can encode a subset of unicode.
* **base64:** Base64 string encoding.
* **binary:** This is the "binary string" format mentioned earlier, and is in the process of being deprecated. Avoid its use.

#### Writing to Buffers:
Given that there is already a buffer created:
```
> var buffer = new Buffer(16);
```
we can start writing strings to it:
```
> buffer.write("Hello", "utf-8")
5
```

The first argument to `buffer.write` is the string to write to the buffer, and the second argument is the string encoding. Default string encoding is `utf-8`.

`buffer.write` returned 5. This means that we wrote to five bytes of the buffer.
```
> buffer.write(" world!", 5, "utf-8")
7
```
When `buffer.write` has 3 arguments, the second argument indicates an offset, or the index of the buffer to start writing at.

#### Reading from Buffers:

**toString:**

Probably the most common way to read buffers is to use the `toString` method, since many buffers contain text:
```
> buffer.toString('utf-8')
'Hello world!\u0000�k\t'
```
Again, the first argument is the encoding. In this case, it can be seen that not the entire buffer was used! Luckily, because we know how many bytes we've written to the buffer, we can simply add more arguments to "stringify" the slice that's actually interesting:
```
> buffer.toString("utf-8", 0, 12)
'Hello world!'
```

#### Buffers Methods:

**Buffer.isBuffer(object)**

This method checks to see if object is a `buffer`, similar to `Array.isArray`.

**Buffer.byteLength(string, encoding)**

With this function, you can check the number of bytes required to encode a string with a given encoding (which defaults to utf-8). This length is not the same as string length, since many characters require more bytes to encode. For example:
```
> var snowman = "☃";
> snowman.length
1
> Buffer.byteLength(snowman)
3
```
The unicode snowman is only one character, but takes 3 entire bytes to encode!

**Buffer.length**

This is the length of your buffer, and represents how much memory is allocated. It is not the same as the size of the buffer's contents, since a buffer may be half-filled. For example:
```
> var buffer = new Buffer(16)
> buffer.write(snowman)
3
> buffer.length
16
```
In this example, the contents written to the buffer only consist of three groups (since they represent the single-character snowman), but the buffer's length is still 16, as it was initialized.

**buffer.copy(target, targetStart=0, sourceStart=0, sourceEnd=buffer.length)**

buffer.copy allows one to copy the contents of one buffer onto another. The first argument is the target buffer on which to copy the contents of buffer, and the rest of the arguments allow for copying only a subsection of the source buffer to somewhere in the middle of the target buffer. For example:
```
> var frosty = new Buffer(24)
> var snowman = new Buffer("☃", "utf-8")
> frosty.write("Happy birthday! ", "utf-8")
16
> snowman.copy(frosty, 16)
3
> frosty.toString("utf-8", 0, 19)
'Happy birthday! ☃'
```
In this example, I copied the "snowman" buffer, which contains a 3 byte long character, to the "frosty" buffer, to which I had written to the first 16 bytes. Because the snowman character is 3 bytes long, the result takes up 19 bytes of the buffer.

**buffer.slice(start, end=buffer.length)**

This method's API is generally the same as that of Array.prototype.slice, but with one very import difference: The slice is not a new buffer and merely references a subset of the memory space. Modifying the slice will also modify the original buffer! For example:
```
> var puddle = frosty.slice(16, 19)
> puddle.toString()
'☃'
> puddle.write("___")
3
> frosty.toString("utf-8", 0, 19)
'Happy birthday! ___'
```

### What are Streams?

Stream in Node.js simply means a sequence of data being moved from one point to the other over time. The whole concept is, you have a huge amount of data to process, but you don’t need to wait for all the data to be available before you start processing it.

Basically, this big data is broken down and sent in chunks. So from the original definition of a buffer (“streams of binary data… in the context of… file system”) this simply means binary data being moved in the file system. For example, moving the texts stored in file1.txt to file2.txt.

#### Types of Streams:
There are four fundamental stream types within Node.js:

* **Readable** - streams from which data can be read (example: `fs.createReadStream()`).

**EXample:**

```javascript
var fs = require("fs");
var data = '';

// Create a readable stream
var readerStream = fs.createReadStream('input.txt');

// Set the encoding to be utf8. 
readerStream.setEncoding('UTF8');

// Handle stream events --> data, end, and error
readerStream.on('data', function(chunk) {
   data += chunk;
});

readerStream.on('end',function(){
   console.log(data);
});

readerStream.on('error', function(err){
   console.log(err.stack);
});

console.log("Program Ended");
```

* **Writable** - streams to which data can be written (example: `fs.createWriteStream()`).

**EXample:**

```javascript
var fs = require("fs");
var data = 'Simply Easy Learning';

// Create a writable stream
var writerStream = fs.createWriteStream('output.txt');

// Write the data to stream with encoding to be utf8
writerStream.write(data,'UTF8');

// Mark the end of file
writerStream.end();

// Handle stream events --> finish, and error
writerStream.on('finish', function() {
    console.log("Write completed.");
});

writerStream.on('error', function(err){
   console.log(err.stack);
});

console.log("Program Ended");
```

* **Duplex** - streams that are both Readable and Writable (example: `net.Socket`).

**EXample:**

```javascript
var fs = require("fs");

// Create a readable stream
var readerStream = fs.createReadStream('input.txt');

// Create a writable stream
var writerStream = fs.createWriteStream('output.txt');

// Pipe the read and write operations
// read input.txt and write data to output.txt
readerStream.pipe(writerStream);

console.log("Program Ended");
```

* **Transform** - Duplex streams that can modify or transform the data as it is written and read (example: `zlib.createDeflate()`).

**EXample:**

```javascript
var fs = require("fs");
var zlib = require('zlib');

// Compress the file input.txt to input.txt.gz
fs.createReadStream('input.txt')
   .pipe(zlib.createGzip())
   .pipe(fs.createWriteStream('input.txt.gz'));
  
console.log("File Compressed.");
```

Each type of Stream is an **EventEmitter** instance and throws several events at different instance of times. For example, some of the commonly used events are −

**data** − This event is fired when there is data is available to read.

**end** − This event is fired when there is no more data to read.

**error** − This event is fired when there is any error receiving or writing data.

**finish** − This event is fired when all the data has been flushed to underlying system.

### What are evets & event emitters?

#### Event:

Node.js allows us to create and handle custom events easily by using `events` module. Event module includes EventEmitter class which can be used to raise and handle custom events.

#### Event Emitters:
In NodeJs, any object that emits an event is an instance of the EventEmitter class which exposes 2 important functionalities:

* The ability to trigger events using eventEmitter.emit(someEvent, optionalData)
* The ability to assign one or more event handlers to a specific event using eventEmitter.on(someEvent, eventHandler)

**For Example:** a `net.Server` object emits an event each time a peer connects to it; a `fs.ReadStream` emits an event when the file is opened; a `stream` emits an event whenever data is available to be read.

Let's have a look:
```javascript
// require the EventEmitter from the events module
const EventEmitter = require('events').EventEmitter

// create an instance of the EventEmitter object
const eventEmitter = new EventEmitter()

// register a listener for the 'randomString' event
eventEmitter.on('randomString', function (randomStr) {
  console.log('Received the string: ' + randomStr)
})

// trigger an event called 'randomString' and send
// a randomly selected string to the listeners
eventEmitter.emit('randomString', randomString())

// simple function to randomly select a string from an array
function randomString () {
  const stringsArr = ['NodeJs', 'coligo.io', 'JavaScript', 'EventEmitters']
  return stringsArr[Math.floor(Math.random() * stringsArr.length)]
}
```

You can alse use `addListener()` method to subscribe for an event. See below example:
```javascript
var emitter = require('events').EventEmitter;

var em = new emitter();

//Subscribe FirstEvent
em.addListener('FirstEvent', function (data) {
    console.log('First subscriber: ' + data);
});

//Subscribe SecondEvent
em.on('SecondEvent', function (data) {
    console.log('First subscriber: ' + data);
});

// Raising FirstEvent
em.emit('FirstEvent', 'This is my first Node.js event emitter example.');

// Raising SecondEvent
em.emit('SecondEvent', 'This is my second Node.js event emitter example.');

```

#### Handling events only once:
```javascript
const eventEmitter = new EventEmitter();
let m = 0;
eventEmitter.once('event', () => {
  console.log(++m);
});
eventEmitter.emit('event');
// Prints: 1
eventEmitter.emit('event');
// Ignored
```

#### Error Events:
```javascript
const eventEmitter = new EventEmitter();
eventEmitter.on('error', (err) => {
  console.error('whoops! there was an error');
});
eventEmitter.emit('error', new Error('whoops!'));
// Prints: whoops! there was an error
```

### How to create an Http Server using Node.js?
Node.js is best for developing HTTP based application. http module is used to create an http server.

```javascript
var http=require("http");
http.createServer(function(req,res){
	res.writeHead(200,{"Content-Type":"text/html"});
	res.write("<h1>Hello, Node.js Http Server!</h1>");
	res.end(); //to end response
}).listen(8081);
console.log("Server is running at http://localhost:8081");
```

### What are Node.js Http module limitations?
Node.js http module has following limitations:

* No cookies handling or parsing.
* No built-in session support.
* No built-in routing supp.
* No static file serving.

### What are middleware in node.js?
Middleware are the functions that are invoked by the Express routing layer before your final request handler is made. Express invokes all the middleware functions each time when client makes a request. 

#### Types of middlewares:

* Application-level middleware
```javascript
var app = express();

//application level middleware for each request
app.use(function (req, res, next) {
  console.log('Time:', Date.now())
  next()
})

//application level middleware for each request mount with /user
app.use('/user/:id', function (req, res, next) {
  console.log('Request Type:', req.method)
  next()
})
```
* Router-level middleware
```javascript
var app = express()
var router = express.Router()

// a middleware function with no mount path. This code is executed for every request to the router
router.use(function (req, res, next) {
  console.log('Time:', Date.now())
  next()
})

// a middleware sub-stack shows request info for any type of HTTP request to the /user/:id path
router.use('/user/:id', function (req, res, next) {
  console.log('Request URL:', req.originalUrl)
  next()
}, function (req, res, next) {
  console.log('Request Type:', req.method)
  next()
})
```
* Error-handling middleware
```javascript
app.use(function (err, req, res, next) {
  console.error(err.stack)
  res.status(500).send('Something broke!')
})
```
* Built-in middleware

**express.static:** serves static assets such as HTML files, images, and so on.

**express.json:** parses incoming requests with JSON payloads. NOTE: Available with Express 4.16.0+

**express.urlencoded:** parses incoming requests with URL-encoded payloads. NOTE: Available with Express 4.16.0+

* Third-party middleware
```javascript
var express = require('express')
var app = express()
var cookieParser = require('cookie-parser')

// load the cookie-parsing middleware
app.use(cookieParser())
```
### What is the difference between exports and module.exports?

Whenever we require any module from one file. By default it returns `module.exports` object that is the reference to that module. Both `exports` and `module.exports` helps to create function or access function in another module.

* `module.exports` returns the complete module as an object
* `exports` returns single property at a time and attaches this property to module.exports

**Example:**
```javascript
//Main.js
Var requireMe = require('./requireMe');

//console.log(module.exports);

requireMe();
requireMe.name(function() {
	console.log('I am back to the main module');
});


//requireMe.js
//It will work
module.exports = function() {
	console.log('It will work');
}

//It will not work
exports = function() {
	console.log('It will not work');
}

//To work correctly we can define as following
exports.name = function() {
	console.log('Now it will work');

}
```
# NodeJS Questions And Answers

### What does npm start in NodeJS?
npm start will run whatever you have defined for the start command of the scripts object in your package.json file.

So if it looks like this:
```JSON
"scripts": {
  "start": "ng serve"
}
```
Then npm start will run ng serve.

### How to get clientId/clientSecret of Gmail account?
Follow the below steps

* Register your Application at Google APIs Console. [click here to register your app]('https://console.developers.google.com/') and create a new project if you don't have and go to API Access & Services Page. see below image: 

![Image Reference](https://drive.google.com/uc?export=view&id=1lomvGQJJkVNVEMykVNTeNjjgjr-5hvMg)

* Click on `OAuth Consent Screeen` and write any product name of your choice and save it. 
  
  **For Example:**
  
  ![Image Reference](https://drive.google.com/uc?export=view&id=1lAbQpko8IJI2WxHhpJ9dISjUZ-0eLXhz)

* Now Select `create cridentials` and select `Oauth Client Id`. Here, when 
  you create a client ID, [Set this URL](https://developers.google.com/oauthplayground) into the text 
  box for Redirect URIs.
  
  See below image for reference:
   
  ![Image Reference](https://drive.google.com/uc?export=view&id=13SMyNiZGq4kONRtz_pxq0UjhVEb4ZWWq)
 

* You must be obtained your client ID & client secret.

* Open Google OAuth2.0 Playground. [Click here]('https://developers.google.com/oauthplayground') to open Google OAuth2.0 Playground Page and click the gear button on the right-top. 

  see reference image:

  ![Image Reference](https://drive.google.com/uc?export=view&id=1GTKRV9Ixe1O3R_aPRyyn_dzaKBcQef0L)

* Set your `clientId` & `clientSecret` that obtained on step 3, and set 
 `Access token location` to `Authorization header w/ Bearer prefix`. Once done, close it.

* **Set up and authorize API:** Select an API from the scope list and click `Authorize API`.
  
  See reference image:
  ![Image Reference](https://drive.google.com/uc?export=view&id=1LBi32eUprrnGUUycc4bgIJk9RqdMgNNa)

* **Obtain the `refresh token`**: After OAuth2.0 authorization, click `Exchange authorization code for tokens` button. You will get your refresh token.

See reference image:

![Image Reference](https://drive.google.com/uc?export=view&id=1NXO7RZFijpRBNTGLHWJ_ITlweT7gHRdp)

* You must obtain `refresh token` and `access Token`.

### How to prevent `GET /favicon.ico` in express application?

Browsers will by default try to request `/favicon.ico` from the root of a hostname, in order to show an icon in the browser tab.

If you want to avoid this request returning a 404, you can either:

* Supply a favicon.ico file that is available at the root of your site.
* Use a module such as serve-favicon to point requests to a specific file.
* Catch the favicon.ico request and send a 204(No Content status):
```javascript
app.get('/favicon.ico', function(req, res) {
    res.snedStatus(204);
});
```

### How to clone github project including submodules?

You can use this command to clone your repo with all the submodules:
```
git clone --recursive YOUR-GIT-REPO-URL
```
Or if you have already cloned the project, you can### What is callback:
A callback is an anonimous function which passed as an argument to an asynchronous function, that describes what
to do after the asynchronous operation has completed. Callbacks are used frequently in node.js development.

```javascript
var fs = require('fs');
//callback function to read file data
fs.readFile('text.txt', 'utf8', function (err, data) { //callback function
	console.log(data);
});
``` use:
```
git submodule init
git submodule update
```

### How to check whether `path_string` is a file or directory?
```javascript
fs.lstatSync(path_string).isDirectory(); //returns true if path_string is a directory. 
fs.lstatSync(path_string).isFile(); //returns true if path_string is a file.
```

### How to set custom favicon in Express?

Install the `favicon` middleware and then do:
```javascript
var favicon = require('serve-favicon');

app.use(favicon(__dirname + '/public/images/favicon.ico'));

//Or better, using the path module:
app.use(favicon(path.join(__dirname,'public','images','favicon.ico')));
```

# NodeJS Pupular Modules
## express
Express is a web framework for NodeJS.

### Installation:

Before installing, download and install Node.js. Node.js `0.10` or higher and npm.

Installation is done using the npm install command:
```
$ npm install express
```
### Hello World Example:
```javascript
var express = require('express')
var app = express()
 
app.get('/', function (req, res) {
  res.send('Hello World')
})
 
app.listen(3000)
```

### Features:

* Robust routing
* Focus on high performance
* Super-high test coverage
* HTTP helpers (redirection, caching, etc)
* View system supporting 14+ template engines
* Content negotiation
* Executable for generating applications quickly

### Basic routing:

Routing refers to determining how an application responds to a client request to a particular endpoint, which is a URI (or path) and a specific HTTP request method (GET, POST, and so on).

Each route can have one or more handler functions, which are executed when the route is matched.

Route definition takes the following structure:

```
app.METHOD(PATH, HANDLER)
```
Where:

* app - is an instance of express.
* METHOD - is an HTTP request method, in lowercase.
* PATH - is a path on the server.
* HANDLER - is the function executed when the route is matched.

The following examples illustrate defining simple routes.

Respond with Hello World! on the homepage:
```javascript
app.get('/', function (req, res) {
  res.send('Hello World!')
})
```
Respond to POST request on the root route (/), the application’s home page:
```javascript
app.post('/', function (req, res) {
  res.send('Got a POST request')
})
```
Respond to a PUT request to the /user route:
```javascript
app.put('/user', function (req, res) {
  res.send('Got a PUT request at /user')
})
```
Respond to a DELETE request to the /user route:
```javascript
app.delete('/user', function (req, res) {
  res.send('Got a DELETE request at /user')
})
```
### Serving static files in Express:

To serve static files such as images, CSS files, and JavaScript files, use the `express.static` built-in middleware function in Express.

The function signature is:
```
express.static(root, [options])
```
The root argument specifies the root directory from which to serve static assets.

For example, use the following code to serve images, CSS files, and JavaScript files in a directory named public:
```javascript
app.use(express.static('public'))
```
To use multiple static assets directories, call the `express.static` middleware function multiple times:
```javascript
app.use(express.static('public'))
app.use(express.static('files'))
```

Express looks up the files in the order in which you set the static directories with the `express.static` middleware function.

### Serving Virtual Path:

To create a virtual path prefix (where the path does not actually exist in the file system) for files that are served by the express.static function, specify a mount path for the static directory, as shown below:
```
app.use('/static', express.static('public'))
```
Now, you can load the files that are in the public directory from the /static path prefix.

### FAQ:
#### How should I structure my application?
We can structure our application in the following ways:

**Routing Listing:**
```javascript
var site = require('./site');
var post = require('./post');
var user = require('./user');

// General
app.get('/', site.index);

// User
app.get('/users', user.list);
app.all('/user/:id/:op?', user.load);
app.get('/user/:id', user.view);
app.get('/user/:id/view', user.view);
app.get('/user/:id/edit', user.edit);
app.put('/user/:id/edit', user.update);

// Posts
app.get('/posts', post.list);
```
**Routing Map:**
```javascript

//route handler
var users = {
  list: function(req, res){
    res.send('user list');
  },

  get: function(req, res){
    res.send('user ' + req.params.uid);
  },

  delete: function(req, res){
    res.send('delete users');
  }
};

var pets = {
  list: function(req, res){
    res.send('user ' + req.params.uid + '\'s pets');
  },

  delete: function(req, res){
    res.send('delete ' + req.params.uid + '\'s pet ' + req.params.pid);
  }
};

//entry point
app.map({
  '/users': {
    get: users.list,
    delete: users.delete,
    '/:uid': {
      get: users.get,
      '/pets': {
        get: pets.list,
        '/:pid': {
          delete: pets.delete
        }
      }
    }
  }
});
```
and 

**MVC style controllers:**

See image for structure:

![MVC Structure](https://github.com/hotam-singh/tutorials/blob/master/images/express1.png)

#### How do I handle 404 responses?
In Express, `404` responses are not the result of an error, so the error-handler middleware will not capture them. This behavior is because a 404 response simply indicates the absence of additional work to do; in other words, Express has executed all middleware functions and routes, and found that none of them responded. All you need to do is add a middleware function at the very bottom of the stack (below all other functions) to handle a 404 response:
```javascript
app.use(function (req, res, next) {
  res.status(404).send("Sorry can't find that!")
})
```
#### How do I setup an error handler?
You define error-handling middleware in the same way as other middleware, except with four arguments instead of three; specifically with the signature `(err, req, res, next)`:
```javascript
app.use(function (err, req, res, next) {
  console.error(err.stack)
  res.status(500).send('Something broke!')
})
```

## cookie-parser
Parse Cookie header and populate `req.cookies` with an object. Optionally you may enable signed cookie support by passing a secret string, which assigns `req.secret` so it may be used by other middleware.

### Installation:
```
$ npm install cookie-parser
```

### API:
```javascript
var express      = require('express')
var cookieParser = require('cookie-parser')
 
var app = express()
app.use(cookieParser())
 
app.get('/', function(req, res) {
  console.log('Cookies: ', req.cookies)
})
 
app.listen(8080)
```
**cookieParser(secret, options)**

* **secret** - a string or array used for signing cookies. This is optional and if not specified, will not parse signed cookies. If a string is provided, this is used as the secret. If an array is provided, an attempt will be made to unsign the cookie with each secret in order.
* **options** - an object that is passed to cookie.parse as the second option.

## body-parser

Node.js body parsing middleware.

Parse incoming request bodies in a middleware before your handlers, available under the `req.body` property.

This module provides the following parsers:

* JSON body parser
* Raw body parser
* Text body parser
* URL-encoded form body parser

### Installation
```
$ npm install body-parser
```
### API

#### bodyParser.json([options])
Returns middleware that only parses json and only looks at requests where the `Content-Type` header matches the type option.

A new body object containing the parsed data is populated on the request object after the middleware (i.e. req.body).

```javascript
var bodyParser = require('body-parser');
bodyParser.json([options]);
```
##### options:
The json function takes an optional options object that may contain any of the following keys:

* **inflate** - When set to `true`, then deflated (compressed) bodies will be inflated; when `false`, deflated bodies are rejected. Defaults to `true`.
* **limit** - Controls the maximum request body size. If this is a number, then the value specifies the number of `bytes`; if it is a string, the value is passed to the bytes library for parsing. Defaults to `100kb`.
* **reviver** - The reviver option is passed directly to `JSON.parse` as the second argument.
* **strict** - When set to `true`, will only accept arrays and objects; when `false` will accept anything JSON.parse accepts. Defaults to `true`.
* **type** - The `type` option is used to determine what media type the middleware will parse. This option can be a function or a string. If a string, type option is passed directly to the `type-is` library and this can be an extension name (like `json`), a mime type (like `application/json`), or a mime type with a wildcard (like `*/*` or `*/json`). If a function, the type option is called as `fn(req)` and the request is parsed if it returns a truthy value. Defaults to `application/json`.
* **verify** - The verify option, if supplied, is called as `verify(req, res, buf, encoding)`, where `buf` is a Buffer of the raw request body and encoding is the encoding of the request. The parsing can be aborted by throwing an error.

#### bodyParser.raw([options])

Returns middleware that parses all bodies as a Buffer and only looks at requests where the Content-Type header matches the type option. This parser supports automatic inflation of gzip and deflate encodings.

##### Options: 
Same as `bodyParser.json([options])`

#### bodyParser.text([options])

Returns middleware that parses all bodies as a string and only looks at requests where the Content-Type header matches the type option. This parser supports automatic inflation of gzip and deflate encodings.

##### Options: 
* **defaultCharset** - Specify the default character set for the text content if the charset is not specified in the `Content-Type` header of the request. Defaults to `utf-8`.

Rest are same as `bodyParser.json([options])`

#### bodyParser.urlencoded([options])

Returns middleware that only parses `urlencoded` bodies and only looks at requests where the `Content-Type` header matches the type option. This parser accepts only `UTF-8` encoding of the body and supports automatic inflation of `gzip` and `deflate` encodings.

A new body object containing the parsed data is populated on the `request` object after the middleware (i.e. `req.body`). This object will contain `key-value` pairs, where the value can be a string or array (when extended is `false`), or any type (when extended is `true`).

##### Options:

* **extended** - 
* **parameterLimit** - The parameterLimit option controls the maximum number of parameters that are allowed in the URL-encoded data. If a request contains more parameters than this value, a 413 will be returned to the client. Defaults to 1000.

## async

Async module originally designed for [NodeJS](#nodejs) to work with asynchronous javascript.

### Installation:
```
$ npm install async --save 
```
## socket.io   
## passport
### What is passport?
`Passport` is an authentication middleware for NodeJS.

**Example:**
```javascript
//server.js:
var passport = require('passsport');
var flash = require('connect-flash');
app.use(passport.initialize());
app.use(passport.session());
app.use(flash());
app.use(function(req, res, next) {
    req.locals.success_msg = req.flash('success_msg');
    req.locals.error_msg = req.flash('error_msg');
    req.locals.error = req.flash('error');
    next();
})

// process the signup form
app.post('/register', passport.authenticate('local-signup', {
    successRedirect : '/profile', // redirect to the secure profile section
    failureRedirect : '/register', // redirect back to the signup page if there is an error
    failureFlash : true // allow flash messages
}));
```

### Passport Authentication:
Passport authenticate requests by calling `passport.authenticate()` and specifying which strategy to employ.

By default, if authentication fails, Passport will respond with a 401 Unauthorized status, and any additional route handlers will not be invoked. If authentication succeeds, the next handler will be invoked and the req.user property will be set to the authenticated user.

**Note:** Strategies must be configured prior to using them in a route

### Strategies:

Strategies are termed strategies to authenticate requests. Strategies range from verifying a username and password, delegated authentication using OAuth or federated authentication using OpenID.

Before asking Passport to authenticate a request, the strategy (or strategies) used by an application must be configured.

Strategies, and their configuration, are supplied via the use() function. **For example**, the following uses the `LocalStrategy` for username/password authentication.

```javascript
var passport = require('passport')
  , LocalStrategy = require('passport-local').Strategy;

passport.use(new LocalStrategy(
  function(username, password, done) {
    User.findOne({ username: username }, function (err, user) {
      if (err) { return done(err); }
      if (!user) {
        return done(null, false, { message: 'Incorrect username.' });
      }
      if (!user.validPassword(password)) {
        return done(null, false, { message: 'Incorrect password.' });
      }
      return done(null, user);
    });
  }
));
```

### Parameters:

By default, LocalStrategy expects to find credentials in parameters named username and password. 

If your site prefers to name these fields differently, options are available to change the defaults.
```javascript
passport.use(new LocalStrategy({
    usernameField: 'email',
    passwordField: 'passwd'
  },
  function(username, password, done) {
    // ...
  }
));
```
### Flash Messages in Passport:

Redirects are often combined with flash messages in order to display status information to the user.

**failureFlash(true/false):**

Setting the failureFlash option to true instructs Passport to flash 
an error message using the message given by the strategy's verify callback.

Alternatively, the flash message can be set manually.
```javascript
passport.authenticate('local', { failureFlash: 'Invalid username or password.' });
```

**successFlash(true/false):**

A successFlash option is available which flashes a success message
when authentication succeeds.
```javascript
passport.authenticate('local', { successFlash: 'Welcome!' });
```
**Note:** Using flash messages requires a req.flash() function. Express 2.x provided this functionality, however it was removed from Express 3.x. Use of connect-flash middleware is recommended to provide this functionality when using Express 3.x or above.

### Disable Sessions:

After successful authentication, Passport will establish a persistent login session. This is useful for the common scenario of users accessing a web application via a browser. 

However, in some cases, session support is not necessary. **For example**, API servers typically require credentials to be supplied with each request. When this is the case, session support can be safely disabled by setting the session option to false.
```javascript
app.get('/api/users/me', passport.authenticate('basic', { session: false }), function(req, res) {
    res.json({ id: req.user.id, username: req.user.username });
});
```
## nodemailer
## mysql
## mongodb
## mongoose
## lodash
## request
## chalk
## bluebird
## commander
## moment
## fs
## q
## winston
## redis
## handlebars
## ejs
## dotenv
## jsonwebtoken
## cors
