1. [NodeJS](#nodejs)
	1. [What is nodejs](#what-is-nodejs)
    1. [What is v8](#what-is-v8)
	2. [NodeJS Pupular Modules](#nodejs-pupular-modules)
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
2. [MongoDB](#mongodb)
3. [AngularJS](#angularjs)
4. [JavaScript](#javascript)
5. [MySQL](#mysql)
6. [PostgreSQL](#postgresql)
7. [Elasticsearch](#Elasticsearch)


# NodeJS

## What is nodejs?
Node.js is a javascript runtime built on chrome’s V8 engine for building fast scalable network application. Node.js uses an event driven, non-blocking I/O model that makes it lightweight and efficient. 

Node.js is basically a library and a runtime environment that allows us to execute javascript on the server.

## What is V8?

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

## What Node.js is not?
* Node.js is not a JavaScript library, but it is a platform to execute JavaScript on server side.
* Node.js programs are written in JavaScript but there is no DOM manipulation provided by Node.js.

## Who has developed Node.js?
Node.js was developed by `Ryan Dahl` and other developers working at `Joyent`. It was first released in 2009
supporting only Linux. In 2011, windows version was released.

## Why Node.js?
**Open Source:** Node.js is open source, so it’s free to use and no need to pay for license. There are also many open
source modules supported by Node.js.

**No need to learn another language for server side code.**

**Non-blocking**

**Very Fast**

**Single threaded but highly scalable:** You can scale your Node.js application by using two ways – `Horizontal Scaling` and `Vertical Scaling`,
which helps you to improve your application performance.

* In Horizontal scaling you can add more nodes to your existing system.
* In Vertical scaling you can add more resources to a single node.

## What are the limitations of Node.js?
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

## what is REPL?
Node.js comes with virtual environment called REPL(Node shell). REPL stands for Read-Eval-Print-Loop. It is an interface to run your JavaScript code and see the results..

You can test pretty much any Node.js/JavaScript expression in REPL. For example, if your write `10 + 20` then it will display result `30` immediately in new line.

**Read-Eval-Print-Loop:**

**Read** − Reads user's input, parses the input into JavaScript data-structure, and stores in memory.

**Eval** − Takes and evaluates the data structure.

**Print** − Prints the result.

**Loop** − Loops the above command until the user presses ctrl-c twice.

The REPL feature of Node is very useful in experimenting with Node.js codes and to debug JavaScript codes.

## What is npm?
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

### Install Modules Using NPM

`$ npm install <module_name>`

**Example:**

`$ npm install express`

### Install Modules Listed in Package.json

`$ npm install`

It will install all modules present in `package.json` file

### Uninstall a Module

`$ npm uninstall <module_name_to_be_uninstalled>`

### Update a Module

`$ npm update <module_name_to_be_updated>`

## How Node.js work?

Traditional Web Server

![Traditional Web Server](https://drive.google.com/uc?export=view&id=1MvyKGX4mFJMFdXdhqc8mPWvj-95sEESp)

Node.js Process Model:

![NodeJS Process Model](https://github.com/hotam-singh/tutorials/blob/master/images/node_2.png)

## Explain Node.js Architecture?
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

## Who are using Node.js for their development?
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

## What is Event Loop. How it works?


Node.js is a single-threaded application, but it can support concurrency via the concept of event and callbacks. These events and callbacks are handled by event loop.
Event Loop: It has main 2 functionalities

* Whatever the task `Web APIs` hands over  to event loop, It simply adds them up in the `callback queue`.
* Looks if `call stack` is free, pick task from the callback queue and puts it into call stack for execution.

![Event Loop](https://github.com/hotam-singh/tutorials/blob/master/images/node_3.png)

### Call Stack: 
Call Stack is only the javascript runtime on server where javascript is run.
#### Web APIs:
Web APIs are those handlers which makes async programming possible. Web APIs are basically callbacks that return response once completed the given task.

### Callback Queue:
callback queue is a queue where all callbacks are queued up. Event loop process tasks from this queue.

## What is callback?
A callback is an anonimous function which passed as an argument to an asynchronous function, that describes what
to do after the asynchronous operation has completed. Callbacks are used frequently in node.js development.

```javascript
var fs = require('fs');
//callback function to read file data
fs.readFile('text.txt', 'utf8', function (err, data) { //callback function
	console.log(data);
});
```

## What is callback-hell?
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

## How to avoid callback-hell?
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
## What Are Buffer?

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

### Where You See Buffers:
In the wild, buffers are usually seen in the context of binary data coming from streams, such as `fs.createReadStream`.

### Usage:
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

### Writing to Buffers:
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

### Reading from Buffers:

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

### Buffers Methods:

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

## What are Streams?

Stream in Node.js simply means a sequence of data being moved from one point to the other over time. The whole concept is, you have a huge amount of data to process, but you don’t need to wait for all the data to be available before you start processing it.

Basically, this big data is broken down and sent in chunks. So from the original definition of a buffer (“streams of binary data… in the context of… file system”) this simply means binary data being moved in the file system. For example, moving the texts stored in file1.txt to file2.txt.

### Types of Streams:
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

## What are evets & event emitters?

### Event:

Node.js allows us to create and handle custom events easily by using `events` module. Event module includes EventEmitter class which can be used to raise and handle custom events.

### Event Emitters:
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

### Handling events only once:
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

### Error Events:
```javascript
const eventEmitter = new EventEmitter();
eventEmitter.on('error', (err) => {
  console.error('whoops! there was an error');
});
eventEmitter.emit('error', new Error('whoops!'));
// Prints: whoops! there was an error
```

## How to create an Http Server using Node.js?
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

## What are Node.js Http module limitations?
Node.js http module has following limitations:

* No cookies handling or parsing.
* No built-in session support.
* No built-in routing supp.
* No static file serving.

## What are middleware in node.js?
Middleware are the functions that are invoked by the Express routing layer before your final request handler is made. Express invokes all the middleware functions each time when client makes a request. 

### Types of middlewares:

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
## What is the difference between exports and module.exports?

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
### Async Methods:
#### auto
**Syntax:**
```
auto(tasks, concurrency(opt), callback(opt)
```
* **tasks:** - An object. Each of its properties is either a function or an array of requirements.

* **concurrency:** - An optional integer for determining the maximum number of tasks that can be run in parallel. By default, as many as possible.

* **callback:** - An optional callback which is called when all the tasks have been completed. It receives the `err` argument if any tasks pass an error to their callback. `Results` are always returned; however, if an `error` occurs, no further tasks will be performed, and the `results` object will only contain partial `results`.

**Definition:**

Determines the best order for running the AsyncFunctions in tasks, based on their requirements. Each function can optionally depend on other functions being completed first, and each function is run as soon as its requirements are satisfied.

If any of the AsyncFunctions pass an error to their callback, the auto sequence will stop. Further tasks will not execute (so any other functions depending on it will not run), and the main callback is immediately called with the error.

AsyncFunctions also receive an object containing the results of functions which have completed so far as the first argument, if they have dependencies. If a task function has no dependencies, it will only be passed a callback.

**Example:**
```javascript
async.auto({
    get_data: function(callback) {
        console.log('in get_data');
        // async code to get some data
        callback(null, 'data', 'converted to array');
    },
    make_folder: function(callback) {
        console.log('in make_folder');
        // async code to create a directory to store a file in
        // this is run at the same time as getting the data
        callback(null, 'folder');
    },
    write_file: ['get_data', 'make_folder', function(results, callback) {
        console.log('in write_file', JSON.stringify(results));
        // once there is some data and the directory exists,
        // write the data to a file in the directory
        callback(null, 'filename');
    }],
    email_link: ['write_file', function(results, callback) {
        console.log('in email_link', JSON.stringify(results));
        // once the file is written let's email a link to it...
        // results.write_file contains the filename returned by write_file.
        callback(null, {'file':results.write_file, 'email':'user@example.com'});
    }]
}, function(err, results) {
    console.log('err = ', err);
    console.log('results = ', results);
});
```

#### forever

**Syntax:**
```
forever(fn, errback(opt))
```
* **fn:** - an async function to call repeatedly. Invoked with (next).

* **errback:** - when `fn` passes an error to it's callback, this function will be called, and execution stops. Invoked with (err).

**Definition:**

Calls the asynchronous function `fn` with a callback parameter that allows it to call itself again, in series, indefinitely. If an error is passed to the callback then `errback` is called with the `error`, and execution stops, otherwise it will never be called.

**Example:**
```javascript
async.forever(
    function(next) {
        // next is suitable for passing to things that need a callback(err [, whatever]);
        // it will result in this function being called again.
    },
    function(err) {
        // if next is called with a value in its first parameter, it will appear
        // in here as 'err', and execution will stop.
    }
);
```

#### parallel

**Syntax:**
```
parallel(tasks, callback(opt))
```
* **tasks:** - A collection of async functions to run. Each async function can complete with any number of optional result values.

* **callback:** - An optional callback to run once all the functions have completed successfully. This function gets a results array (or object) containing all the result arguments passed to the task callbacks. Invoked with (err, results).

**Definition:**

Run the tasks collection of functions in parallel, without waiting until the previous function has completed. If any of the functions pass an error to its callback, the main callback is immediately called with the value of the error. Once the tasks have completed, the results are passed to the final callback as an array.

**Note:** parallel is about kicking-off I/O tasks in parallel, not about parallel execution of code. If your tasks do not use any timers or perform any I/O, they will actually be executed in series. Any synchronous setup sections for each task will happen one after the other. JavaScript remains single-threaded.

**Hint:** Use reflect to continue the execution of other tasks when a task fails.

It is also possible to use an object instead of an array. Each property will be run as a function and the results will be passed to the final callback as an object instead of an array. This can be a more readable way of handling results from async.parallel.

**Example:**
```javascript
async.parallel([
    function(callback) {
        setTimeout(function() {
            callback(null, 'one');
        }, 200);
    },
    function(callback) {
        setTimeout(function() {
            callback(null, 'two');
        }, 100);
    }
],
// optional callback
function(err, results) {
    // the results array will equal ['one','two'] even though
    // the second function had a shorter timeout.
});

// an example using an object instead of an array
async.parallel({
    one: function(callback) {
        setTimeout(function() {
            callback(null, 1);
        }, 200);
    },
    two: function(callback) {
        setTimeout(function() {
            callback(null, 2);
        }, 100);
    }
}, function(err, results) {
    // results is now equals to: {one: 1, two: 2}
});
```

#### series

**Syntax:**
```
series(tasks, callback(opt))

```
* **tasks:** - A collection containing async functions to run in series. Each function can complete with any number of optional result values.

* **callback:** - An optional callback to run once all the functions have completed. This function gets a results array (or object) containing all the result arguments passed to the task callbacks. Invoked with (err, result).

**Definition:**

Run the functions in the tasks collection in series, each one running once the previous function has completed. If any functions in the series pass an error to its callback, no more functions are run, and callback is immediately called with the value of the error. Otherwise, callback receives an array of results when tasks have completed.

It is also possible to use an object instead of an array. Each property will be run as a function, and the results will be passed to the final callback as an object instead of an array. This can be a more readable way of handling results from async.series.

**Example:**
```javascript
async.series([
    function(callback) {
        // do some stuff ...
        callback(null, 'one');
    },
    function(callback) {
        // do some more stuff ...
        callback(null, 'two');
    }
],
// optional callback
function(err, results) {
    // results is now equal to ['one', 'two']
});

async.series({
    one: function(callback) {
        setTimeout(function() {
            callback(null, 1);
        }, 200);
    },
    two: function(callback){
        setTimeout(function() {
            callback(null, 2);
        }, 100);
    }
}, function(err, results) {
    // results is now equal to: {one: 1, two: 2}
});
```

#### waterfall

**Syntax:**
```
waterfall(tasks, callback(opt))

```
* **tasks:** - An array of async functions to run. Each function should complete with any number of result values. The result values will be passed as arguments, in order, to the next task.

* **callback:** - An optional callback to run once all the functions have completed. This will be passed the results of the last task's callback. Invoked with `(err, [results])`.

**Definition:**

Run the functions in the tasks collection in series, each one running once the previous function has completed. If any functions in the series pass an error to its callback, no more functions are run, and callback is immediately called with the value of the error. Otherwise, callback receives an array of results when tasks have completed.

It is also possible to use an object instead of an array. Each property will be run as a function, and the results will be passed to the final callback as an object instead of an array. This can be a more readable way of handling results from async.series.

**Example:**
```javascript
async.series([
    function(callback) {
        // do some stuff ...
        callback(null, 'one');
    },
    function(callback) {
        // do some more stuff ...
        callback(null, 'two');
    }
],
// optional callback
function(err, results) {
    // results is now equal to ['one', 'two']
});

async.series({
    one: function(callback) {
        setTimeout(function() {
            callback(null, 1);
        }, 200);
    },
    two: function(callback){
        setTimeout(function() {
            callback(null, 2);
        }, 100);
    }
}, function(err, results) {
    // results is now equal to: {one: 1, two: 2}
});
```

## socket.io   
Socket.IO enables real-time bidirectional event-based communication. It consists in:

* a Node.js server.
* a Javascript client library for the browser (or a Node.js client).

### Features

**Reliability:**

Connections are established even in the presence of:

* proxies and load balancers.
* personal firewall and antivirus software.

For this purpose, it relies on [engine.io](#engineio), which first establishes a long-polling connection, then tries to upgrade to better transports that are "tested" on the side, like WebSocket.

**Auto-reconnection support:**

Unless instructed otherwise a disconnected client will try to reconnect forever, until the server is available again. Please see the available reconnection options.

**Disconnection detection:**

A heartbeat mechanism is implemented at the [engine.io](#engineio) level, allowing both the server and the client to know when the other one is not responding anymore. 

That functionality is achieved with timers set on both the server and the client, with timeout values (the `pingInterval` and `pingTimeout` parameters) shared during the connection handshake.

**Binary support:**

Any serializable data structures can be emitted, including:

* `ArrayBuffer` and `Blob` in the browser
* `ArrayBuffer` and `Buffer` in Node.js

**Simple and convenient API:**

Sample code:
```javascript
io.on('connection', function(socket){
  socket.emit('request', /* */); // emit an event to the socket
  io.emit('broadcast', /* */); // emit an event to all connected sockets
  socket.on('reply', function(){ /* */ }); // listen to the event
});
```

### Installation
```
$ npm install socket.io --save
```

### Using with Node http server
Server (app.js)

```javascript
var app = require('http').createServer(handler)
var io = require('socket.io')(app);
var fs = require('fs');

app.listen(80);

function handler (req, res) {
  fs.readFile(__dirname + '/index.html',
  function (err, data) {
    if (err) {
      res.writeHead(500);
      return res.end('Error loading index.html');
    }

    res.writeHead(200);
    res.end(data);
  });
}

io.on('connection', function (socket) {
  socket.emit('news', { hello: 'world' });
  socket.on('my other event', function (data) {
    console.log(data);
  });
});
```
Client (index.html)
```html
<script src="/socket.io/socket.io.js"></script>
<script>
  var socket = io('http://localhost');
  socket.on('news', function (data) {
    console.log(data);
    socket.emit('my other event', { my: 'data' });
  });
</script>
```

### Using with Express 3/4
Server (app.js)

```javascript
var app = require('express')();
var server = require('http').Server(app);
var io = require('socket.io')(server);

server.listen(80);

app.get('/', function (req, res) {
  res.sendfile(__dirname + '/index.html');
});

io.on('connection', function (socket) {
  socket.emit('news', { hello: 'world' });
  socket.on('my other event', function (data) {
    console.log(data);
  });
});
```

Client (index.html)

```html
<script src="/socket.io/socket.io.js"></script>
<script>
  var socket = io.connect('http://localhost');
  socket.on('news', function (data) {
    console.log(data);
    socket.emit('my other event', { my: 'data' });
  });
</script>
```

### Sending and receiving events
Socket.IO allows you to emit and receive custom events. Besides `connect`, `message` and `disconnect`, you can emit custom events:

Server

```javascript
// note, io(<port>) will create a http server for you
var io = require('socket.io')(80);

io.on('connection', function (socket) {
  io.emit('this', { will: 'be received by everyone'});

  socket.on('private message', function (from, msg) {
    console.log('I received a private message by ', from, ' saying ', msg);
  });

  socket.on('disconnect', function () {
    io.emit('user disconnected');
  });
});
```
### Restricting yourself to a namespace
If you have control over all the messages and events emitted for a particular application, using the default / namespace works. If you want to leverage 3rd-party code, or produce code to share with others, socket.io provides a way of namespacing a socket.

This has the benefit of multiplexing a single connection. Instead of socket.io using two WebSocket connections, it’ll use one.

Server (app.js)

```javascript
var io = require('socket.io')(80);
var chat = io
  .of('/chat')
  .on('connection', function (socket) {
    socket.emit('a message', {
        that: 'only'
      , '/chat': 'will get'
    });
    chat.emit('a message', {
        everyone: 'in'
      , '/chat': 'will get'
    });
  });

var news = io
  .of('/news')
  .on('connection', function (socket) {
    socket.emit('item', { news: 'item' });
  });
```

Client (index.html)

```html
<script>
  var chat = io.connect('http://localhost/chat')
    , news = io.connect('http://localhost/news');
  
  chat.on('connect', function () {
    chat.emit('hi!');
  });
  
  news.on('news', function () {
    news.emit('woot');
  });
</script>
```      

### Broadcasting messages
To broadcast, simply add a broadcast flag to emit and send method calls. Broadcasting means sending a message to everyone else except for the socket that starts it.

Server

```javascript
var io = require('socket.io')(80);

io.on('connection', function (socket) {
  socket.broadcast.emit('user connected');
});
```

## engine.io

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
Nodemailer is a popular module for [NodeJS](#nodejs) applications to send email. Nodemailer is licensed under MIT license.

### Installation
```
$ npm install nodemailer --save
```

### Features

* A single module with `zero dependencies`.
* Heavy focus on `security`.
* `Unicode support` to use any characters, including emoji 💪
* Use HTML content, as well as plain text.
* Add `Attachments` to messages.
* Embedded `image` attachments for HTML content.
* Secure email delivery using `TLS/STARTTLS`.
* Different transport methods in addition to the `built-in SMTP support`.
* Sign messages with `DKIM`
* Sane `OAuth2` authentication
* Proxies for SMTP connections
* `ES6 code` – no more unintentional memory leaks.

### Pre Requirements

Node.js v6+. That’s it.

**Example:**
```javascript
'use strict';
const nodemailer = require('nodemailer');

// Generate test SMTP service account from ethereal.email
// Only needed if you don't have a real mail account for testing
nodemailer.createTestAccount((err, account) => {
    // create reusable transporter object using the default SMTP transport
    let transporter = nodemailer.createTransport({
        host: 'smtp.ethereal.email',
        port: 587,
        secure: false, // true for 465, false for other ports
        auth: {
            user: account.user, // generated ethereal user
            pass: account.pass // generated ethereal password
        }
    });

    // setup email data with unicode symbols
    let mailOptions = {
        from: '"Fred Foo 👻" <foo@example.com>', // sender address
        to: 'bar@example.com, baz@example.com', // list of receivers
        subject: 'Hello ✔', // Subject line
        text: 'Hello world?', // plain text body
        html: '<b>Hello world?</b>' // html body
    };

    // send mail with defined transport object
    transporter.sendMail(mailOptions, (error, info) => {
        if (error) {
            return console.log(error);
        }
        console.log('Message sent: %s', info.messageId);
        // Preview only available when sending through an Ethereal account
        console.log('Preview URL: %s', nodemailer.getTestMessageUrl(info));

        // Message sent: <b658f8ca-6296-ccf4-8306-87d57a0b4321@example.com>
        // Preview URL: https://ethereal.email/message/WaQKMgKddxQDoou...
    });
});
```

### Usage
To send emails you need to follow below steps:
#### 1. create a transporter object
```javascript
let transporter = nodemailer.createTransport(transport[, defaults])
```
Where:

* **transporter** - is going to be an object that is able to send mail
* **transport** - is the transport configuration object, connection url or a transport plugin instance
* **defaults** - is an object that defines default values for mail options

#### Message Configuration

The following are the possible fields of an email message:

Commmon fields:

* **from** - The email address of the sender. All email addresses can be plain ‘sender@server.com’ or formatted ’“Sender Name” sender@server.com‘, see Address object for details
* **to** - Comma separated list or an array of recipients email addresses that will appear on the To: field
* **cc** - Comma separated list or an array of recipients email addresses that will appear on the Cc: field
* **bcc** - Comma separated list or an array of recipients email addresses that will appear on the Bcc: field
* **subject** - The subject of the email
* **text** - The plaintext version of the message as an Unicode string, Buffer, Stream or an attachment-like object ({path: ‘/var/data/…’})
* **html** - The HTML version of the message as an Unicode string, Buffer, Stream or an attachment-like object ({path: ‘http://…‘})
* **attachments** - An array of attachment objects (see Using attachments for details). Attachments can be used for embedding images as well.

A large majority of emails sent look a lot like this, using only a few basic fields:

```javascript
var message = {
    from: 'sender@server.com',
    to: 'receiver@sender.com',
    subject: 'Message title',
    text: 'Plaintext version of the message',
    html: '<p>HTML version of the message</p>'
};
```

#### 3. Sending mail
Once you have a transporter object you can send mail with it:

```javascript
transporter.sendMail(data[, callback])
```

Where

* **data** - defines the mail content (see [Message Configuration](#message-configuration) for possible options)
* **callback** - is an optional callback function to run once the message is delivered or it failed
	* **err** - is the error object if message failed
	* **info** - includes the result, the exact format depends on the transport mechanism used
		* **info.messageId** - most transports should return the final Message-Id value used with this property
		* **info.envelope** - includes the envelope object for the message
		* **info.accepted** - is an array returned by SMTP transports (includes recipient addresses that were accepted by the server)
		* **info.rejected** - is an array returned by SMTP transports (includes recipient addresses that were rejected by the server)
		* **info.pending** - is an array returned by Direct SMTP transport. Includes recipient addresses that were temporarily rejected together with the server response
		* **response** - is a string returned by SMTP transports and includes the last SMTP response from the server

### Sending Emails Using Gmail

**Example 1**
```javascript
var nodemailer = require('nodemailer');
var tarnsporter = nodemailer.createTransport({
	service: 'gmail',
	auth: {
		user: 'YOUR_GMAIL_ADDRESS',
		pass: 'GMAIL_PASSWORD'
	}
});

var mailOptions = {
	from: 'sender@gmail.com', // sender address
    to: 'receiver@server.com', // list of receivers
   	subject: 'Hello', // Subject line
   	text: 'Hello world !', // plain text body
   	html: '<b>Hello world !</b>' // html body
};

tarnsporter.sendMail(mailOptions, function(err, info) {
	if(err) {
		console.log('error : '+err);
		return;
	}
	console.log('mail sent successfully');
});
```

### Sending Email Using OAuth2
```javascript
var nodemailer = require('nodemailer');

var transporter = nodemailer.createTransport({
    host: 'smtp.gmail.com',
    port: 465,
    secure: true,
    auth: {
        type: 'OAuth2',
        clientId: ENV.CLIENTID,
        clientSecret: ENV.CLIENTSECRET
    }
  });


var mailOptions = {
	from: 'sender@gmail.com', // sender address
    to: 'reciever@gmail.com', // list of receivers
    subject: 'Hello', // Subject line
    text: 'Hello world ?', // plain text body
    html: '<b>Hello world ?</b>', 
    auth: {
        user: 'sender@gmail.com',
        refreshToken: ENV.REFRESHTOKEN,
        accessToken: ENV.ACCESSTOKEN
    }
};

transporter.sendMail(mailOptions, function(err, info) {
	if(err) {
		console.log('error : '+err);
		return;
	}
	console.log('mail sent successfully');
});
```

## mysql
### Introduction

This is a node.js driver for mysql. It is written in JavaScript, does not require compiling, and is 100% MIT licensed.

Here is an example on how to use it:

```javascript
var mysql      = require('mysql');
var connection = mysql.createConnection({
  host     : 'localhost',
  user     : 'me',
  password : 'secret',
  database : 'my_db'
});
 
connection.connect();
 
connection.query('SELECT 1 + 1 AS solution', function (error, results, fields) {
  if (error) throw error;
  console.log('The solution is: ', results[0].solution);
});
 
connection.end();
```

### Installation
```
$ npm install mysql
```

### Establishing connections
The recommended way to establish a connection is this:

```javascript
var mysql      = require('mysql');
var connection = mysql.createConnection({
  host     : 'example.org',
  user     : 'bob',
  password : 'secret'
});
 
connection.connect(function(err) {
  if (err) {
    console.error('error connecting: ' + err.stack);
    return;
  }
 
  console.log('connected as id ' + connection.threadId);
});
```

However, a connection can also be implicitly established by invoking a query:

```javascript
var mysql      = require('mysql');
var connection = mysql.createConnection(...);
 
connection.query('SELECT 1', function (error, results, fields) {
  if (error) throw error;
  // connected!
});
```

### Connection options

When establishing a connection, you can set the following options:

* **host:** The hostname of the database you are connecting to. (Default: localhost)
* **port:** The port number to connect to. (Default: 3306)
* **localAddress:** The source IP address to use for TCP connection. (Optional)
* **socketPath:** The path to a unix domain socket to connect to. When used host and port are ignored.
* **user:** The MySQL user to authenticate as.
* **password:** The password of that MySQL user.
* **database:** Name of the database to use for this connection (Optional).
* **charset:** The charset for the connection. This is called "collation" in the SQL-level of MySQL (like utf8_general_ci). If a SQL-level charset is specified (like utf8mb4) then the default collation for that charset is used. (Default: 'UTF8_GENERAL_CI')
* **timezone:** The timezone configured on the MySQL server. This is used to type cast server date/time values to JavaScript Date object and vice versa. This can be 'local', 'Z', or an offset in the form +HH:MM or -HH:MM. (Default: 'local')
* **connectTimeout:** The milliseconds before a timeout occurs during the initial connection to the MySQL server. (Default: 10000)
* **stringifyObjects:** Stringify objects instead of converting to values. See issue #501. (Default: false)
* **insecureAuth:** Allow connecting to MySQL instances that ask for the old (insecure) authentication method. (Default: false)
* **typeCast:** Determines if column values should be converted to native JavaScript types. (Default: true)
* **queryFormat:** A custom query format function. See Custom format.
* **supportBigNumbers:** When dealing with big numbers (BIGINT and DECIMAL columns) in the database, you should enable this option (Default: false).
* **bigNumberStrings:** Enabling both supportBigNumbers and bigNumberStrings forces big numbers (BIGINT and DECIMAL columns) to be always returned as JavaScript String objects (Default: false). Enabling supportBigNumbers but leaving bigNumberStrings disabled will return big numbers as String objects only when they cannot be accurately represented with JavaScript Number objects (which happens when they exceed the [-2^53, +2^53] range), otherwise they will be returned as Number objects. This option is ignored if supportBigNumbers is disabled.
* **dateStrings:** Force date types (TIMESTAMP, DATETIME, DATE) to be returned as strings rather then inflated into JavaScript Date objects. Can be true/false or an array of type names to keep as strings. (Default: false)
* **debug:** Prints protocol details to stdout. Can be true/false or an array of packet type names that should be printed. (Default: false)
* **trace:** Generates stack traces on Error to include call site of library entrance ("long stack traces"). Slight performance penalty for most calls. (Default: true)
* **multipleStatements:** Allow multiple mysql statements per query. Be careful with this, it could increase the scope of SQL injection attacks. (Default: false)
* **flags:** List of connection flags to use other than the default ones. It is also possible to blacklist default ones. For more information, check Connection Flags.
* **ssl:** object with ssl parameters or a string containing name of ssl profile.

In addition to passing these options as an object, you can also use a url string. For example:

```javascript
var connection = mysql.createConnection('mysql://user:pass@host/db?debug=true&charset=BIG5_CHINESE_CI&timezone=-0700');
```

### SSL Option

```javascript
var connection = mysql.createConnection({
  host : 'localhost',
  ssl  : {
    ca : fs.readFileSync(__dirname + '/mysql-ca.crt')
  }
});
```

You can also connect to a MySQL server without properly providing the appropriate CA to trust. You should not do this.

```javascript
var connection = mysql.createConnection({
  host : 'localhost',
  ssl  : {
    // DO NOT DO THIS
    // set up your ca correctly to trust the connection
    rejectUnauthorized: false
  }
});
```

### Pooling connections
Rather than creating and managing connections one-by-one, this module also provides built-in connection pooling using mysql.createPool(config). Read more about connection pooling.

Use pool directly.

```javascript
var mysql = require('mysql');
var pool  = mysql.createPool({
  connectionLimit : 10,
  host            : 'example.org',
  user            : 'bob',
  password        : 'secret',
  database        : 'my_db'
});
 
pool.query('SELECT 1 + 1 AS solution', function (error, results, fields) {
  if (error) throw error;
  console.log('The solution is: ', results[0].solution);
});
```

Connections can be pooled to ease sharing a single connection, or managing multiple connections.

```javascript
var mysql = require('mysql');
var pool  = mysql.createPool({
  host     : 'example.org',
  user     : 'bob',
  password : 'secret',
  database : 'my_db'
});
 
pool.getConnection(function(err, connection) {
  // connected! (unless `err` is set)
});
```

When you are done with a connection, just call connection.release() and the connection will return to the pool, ready to be used again by someone else.

```javascript
var mysql = require('mysql');
var pool  = mysql.createPool(...);
 
pool.getConnection(function(err, connection) {
  // Use the connection
  connection.query('SELECT something FROM sometable', function (error, results, fields) {
    // And done with the connection.
    connection.release();
 
    // Handle error after the release.
    if (error) throw error;
 
    // Don't use the connection here, it has been returned to the pool.
  });
});
```

If you would like to close the connection and remove it from the pool, use connection.destroy() instead. The pool will create a new connection the next time one is needed.

### Pool events

#### acquire

The pool will emit an acquire event when a connection is acquired from the pool. This is called after all acquiring activity has been performed on the connection, right before the connection is handed to the callback of the acquiring code.
```javascript
pool.on('acquire', function (connection) {
  console.log('Connection %d acquired', connection.threadId);
});
```


#### connection
The pool will emit a connection event when a new connection is made within the pool. If you need to set session variables on the connection before it gets used, you can listen to the connection event.

```javascript
pool.on('connection', function (connection) {
  connection.query('SET SESSION auto_increment_increment=1')
});
```

#### enqueue
The pool will emit an enqueue event when a callback has been queued to wait for an available connection.

```javascript
pool.on('enqueue', function () {
  console.log('Waiting for available connection slot');
});
```

### release
The pool will emit a release event when a connection is released back to the pool. This is called after all release activity has been performed on the connection, so the connection will be listed as free at the time of the event.

```javascript
pool.on('release', function (connection) {
  console.log('Connection %d released', connection.threadId);
});
```

### Performing queries

The most basic way to perform a query is to call the `.query()` method on an object (like a Connection, Pool, or PoolNamespace instance).

The simplest form of `.query()` is `.query(sqlString, callback)`, where a SQL string is the first argument and the second is a callback:

```javascript
connection.query('SELECT * FROM `books` WHERE `author` = "David"', function (error, results, fields) {
  // error will be an Error if one occurred during the query
  // results will contain the results of the query
  // fields will contain information about the returned results fields (if any)
});
```

The second form `.query(sqlString, values, callback)` comes when using placeholder values (see escaping query values):

```javascript
connection.query('SELECT * FROM `books` WHERE `author` = ?', ['David'], function (error, results, fields) {
  // error will be an Error if one occurred during the query
  // results will contain the results of the query
  // fields will contain information about the returned results fields (if any)
});
```

The third form `.query(options, callback)` comes when using various advanced options on the query, like escaping query values, joins with overlapping column names, timeouts, and type casting.

```javascript
connection.query({
  sql: 'SELECT * FROM `books` WHERE `author` = ?',
  timeout: 40000, // 40s
  values: ['David']
}, function (error, results, fields) {
  // error will be an Error if one occurred during the query
  // results will contain the results of the query
  // fields will contain information about the returned results fields (if any)
});
```

Note that a combination of the second and third forms can be used where the placeholder values are passed as an argument and not in the options object. The values argument will override the values in the option object.

```javascript
connection.query({
    sql: 'SELECT * FROM `books` WHERE `author` = ?',
    timeout: 40000, // 40s
  },
  ['David'],
  function (error, results, fields) {
    // error will be an Error if one occurred during the query
    // results will contain the results of the query
    // fields will contain information about the returned results fields (if any)
  });
```

### Preparing Queries

You can use `mysql.format` to prepare a query with multiple insertion points, utilizing the proper escaping for ids and values. A simple example of this follows:

```javascript
var sql = "SELECT * FROM ?? WHERE ?? = ?";
var inserts = ['users', 'id', userId];
sql = mysql.format(sql, inserts);
```

Following this you then have a valid, escaped query that you can then send to the database safely. This is useful if you are looking to prepare the query before actually sending it to the database. As `mysql.format` is exposed from `SqlString.format` you also have the option (but are not required) to pass in stringifyObject and timezone, allowing you provide a custom means of turning objects into strings, as well as a location-specific/timezone-aware Date.

## mongodb

The official MongoDB driver for Node.js. Provides a high-level API on top of mongodb-core

### MongoDB Node.JS Driver
| what  | where  |
|---|---|
| documentation  | http://mongodb.github.io/node-mongodb-native  | 
| api-doc  | http://mongodb.github.io/node-mongodb-native/3.0/api  | 
|  source | https://github.com/mongodb/node-mongodb-native  | 
| mongodb |  http://www.mongodb.org  |

### Installation
```
$ npm install mongodb --save
```

If all the steps complete, you have the right toolchain installed. If you get the error `Error : node-gyp not found` you need to install `node-gyp` globally:
```
npm install -g node-gyp
```

If it still fails the next step is to examine the npm log. Rerun the command but in this case in verbose mode.
```
npm --loglevel verbose install mongodb
```
### Connect to MongoDB

Create a new `app.js` file and add the following code to try out some basic CRUD operations using the MongoDB driver.

Add code to connect to the server and the database myproject:

```javascript
const MongoClient = require('mongodb').MongoClient;
const assert = require('assert');
 
// Connection URL
const url = 'mongodb://localhost:27017';
 
// Database Name
const dbName = 'myproject';
 
// Use connect method to connect to the server
MongoClient.connect(url, function(err, client) {
  assert.equal(null, err);
  console.log("Connected successfully to server");
 
  const db = client.db(dbName);
 
  client.close();
});
```

Run your app from the command line with:
```
node app.js
```
The application should print `Connected successfully to server` to the console.

### Insert a Document

Add to `app.js` the following function which uses the insertMany method to add three documents to the documents collection.

```javascript
const insertDocuments = function(db, callback) {
  // Get the documents collection
  const collection = db.collection('documents');
  // Insert some documents
  collection.insertMany([
    {a : 1}, {a : 2}, {a : 3}
  ], function(err, result) {
    assert.equal(err, null);
    assert.equal(3, result.result.n);
    assert.equal(3, result.ops.length);
    console.log("Inserted 3 documents into the collection");
    callback(result);
  });
}
```
The insert command returns an object with the following fields:

* **result** - Contains the result document from MongoDB
* **ops** - Contains the documents inserted with added _id fields
* **connection** - Contains the connection used to perform the insert

Add the following code to call the insertDocuments function:

```javascript
const MongoClient = require('mongodb').MongoClient;
const assert = require('assert');
 
// Connection URL
const url = 'mongodb://localhost:27017';
 
// Database Name
const dbName = 'myproject';
 
// Use connect method to connect to the server
MongoClient.connect(url, function(err, client) {
  assert.equal(null, err);
  console.log("Connected successfully to server");
 
  const db = client.db(dbName);
 
  insertDocuments(db, function() {
    client.close();
  });
});
```

Run the updated `app.js` file:
```
node app.js
```

The operation returns the following output:
```
Connected successfully to server
Inserted 3 documents into the collection
```
### Find All Documents

Add a query that returns all the documents.

```javascript
const findDocuments = function(db, callback) {
  // Get the documents collection
  const collection = db.collection('documents');
  // Find some documents
  collection.find({}).toArray(function(err, docs) {
    assert.equal(err, null);
    console.log("Found the following records");
    console.log(docs)
    callback(docs);
  });
}
```

This query returns all the documents in the documents collection. Add the findDocument method to the MongoClient.connect callback:

```javascript
const MongoClient = require('mongodb').MongoClient;
const assert = require('assert');
 
// Connection URL
const url = 'mongodb://localhost:27017';
 
// Database Name
const dbName = 'myproject';
 
// Use connect method to connect to the server
MongoClient.connect(url, function(err, client) {
  assert.equal(null, err);
  console.log("Connected correctly to server");
 
  const db = client.db(dbName);
 
  insertDocuments(db, function() {
    findDocuments(db, function() {
      client.close();
    });
  });
});
```
### Find Documents with a Query Filter

Add a query filter to find only documents which meet the query criteria.

```javascript
const findDocuments = function(db, callback) {
  // Get the documents collection
  const collection = db.collection('documents');
  // Find some documents
  collection.find({'a': 3}).toArray(function(err, docs) {
    assert.equal(err, null);
    console.log("Found the following records");
    console.log(docs);
    callback(docs);
  });
}
```

Only the documents which match `'a' : 3` should be returned.

### Update a document

The following operation updates a document in the documents collection.

```javascript
const updateDocument = function(db, callback) {
  // Get the documents collection
  const collection = db.collection('documents');
  // Update document where a is 2, set b equal to 1
  collection.updateOne({ a : 2 }
    , { $set: { b : 1 } }, function(err, result) {
    assert.equal(err, null);
    assert.equal(1, result.result.n);
    console.log("Updated the document with the field a equal to 2");
    callback(result);
  });  
}
```
Next, update the callback function from `MongoClient.connect` to include the update method.

```javascript
const MongoClient = require('mongodb').MongoClient;
const assert = require('assert');
 
// Connection URL
const url = 'mongodb://localhost:27017';
 
// Database Name
const dbName = 'myproject';
 
// Use connect method to connect to the server
MongoClient.connect(url, function(err, client) {
  assert.equal(null, err);
  console.log("Connected successfully to server");
 
  const db = client.db(dbName);
 
  insertDocuments(db, function() {
    updateDocument(db, function() {
      client.close();
    });
  });
});
```
### Remove a document

Remove the document where the field a is equal to 3.

```javascript
const removeDocument = function(db, callback) {
  // Get the documents collection
  const collection = db.collection('documents');
  // Delete document where a is 3
  collection.deleteOne({ a : 3 }, function(err, result) {
    assert.equal(err, null);
    assert.equal(1, result.result.n);
    console.log("Removed the document with the field a equal to 3");
    callback(result);
  });    
}
```

Add the new method to the `MongoClient.connect` callback function.

```javascript
const MongoClient = require('mongodb').MongoClient;
const assert = require('assert');
 
// Connection URL
const url = 'mongodb://localhost:27017';
 
// Database Name
const dbName = 'myproject';
 
// Use connect method to connect to the server
MongoClient.connect(url, function(err, client) {
  assert.equal(null, err);
  console.log("Connected successfully to server");
 
  const db = client.db(dbName);
 
  insertDocuments(db, function() {
    updateDocument(db, function() {
      removeDocument(db, function() {
        client.close();
      });
    });
  });
});
```
### Index a Collection

Indexes can improve your application's performance. The following function creates an index on the a field in the documents collection.

```javascript
const indexCollection = function(db, callback) {
  db.collection('documents').createIndex(
    { "a": 1 },
      null,
      function(err, results) {
        console.log(results);
        callback();
    }
  );
};
```

Add the indexCollection method to your app:

```javascript
const MongoClient = require('mongodb').MongoClient;
const assert = require('assert');
 
// Connection URL
const url = 'mongodb://localhost:27017';
 
const dbName = 'myproject';
 
// Use connect method to connect to the server
MongoClient.connect(url, function(err, client) {
  assert.equal(null, err);
  console.log("Connected successfully to server");
 
  const db = client.db(dbName);
 
  insertDocuments(db, function() {
    indexCollection(db, function() {
      client.close();
    });
  });
});
```

## mongoose

Mongoose is a MongoDB object modeling tool designed to work in an asynchronous environment.

### Documentation

[mongoosejs.com](http://mongoosejs.com/)

### Importing mongoose
```javascript
// Using Node.js `require()`
const mongoose = require('mongoose');
 
// Using ES6 imports
import mongoose from 'mongoose';
```

### Installation
First install node.js and mongodb. Then:

```
$ npm install mongoose
```

### Connecting to MongoDB
First, we need to define a connection. If your app uses only one database, you should use `mongoose.connect`. If you need to create additional connections, use `mongoose.createConnection`.

Both `connect` and `createConnection` take a mongodb:// URI, or the parameters host, database, port, options.

```javascript
//Importing mongoose
const mongoose = require('mongoose');

//Connect to MongoDB
mongoose.connect('mongodb://localhost/my_database');
```


Once connected, the `open` event is fired on the `Connection` instance. If you're using `mongoose.connect`, the Connection is `mongoose.connection`. Otherwise, `mongoose.createConnection` return value is a `Connection`.

**Note:** If the local connection fails then try using `127.0.0.1` instead of `localhost`. Sometimes issues may arise when the local hostname has been changed.

**Important!** - Mongoose buffers all the commands until it's connected to the database. This means that you don't have to wait until it connects to MongoDB in order to define models, run queries, etc.

### Defining a Model
Models are defined through the `Schema` interface.

```javascript
const Schema = mongoose.Schema,
    ObjectId = Schema.ObjectId;
 
const BlogPost = new Schema({
 author: ObjectId,
 title: String,
 body: String,
 date: Date
});
```
The following example shows some of these features:
```javascript
const Comment = new Schema({
  name: { type: String, default: 'hahaha' },
  age: { type: Number, min: 18, index: true },
  bio: { type: String, match: /[a-z]/ },
  date: { type: Date, default: Date.now },
  buff: Buffer
});
 
// a setter
Comment.path('name').set(function (v) {
  return capitalize(v);
});
 
// middleware
Comment.pre('save', function (next) {
  notify(this.get('email'));
  next();
});
```
### Embedded Documents
```javascript
// retrieve my model
var BlogPost = mongoose.model('BlogPost');
 
// create a blog post
var post = new BlogPost();
 
// create a comment
post.comments.push({ title: 'My comment' });
 
post.save(function (err) {
  if (!err) console.log('Success!');
});
```
The same goes for removing them:
```javascript
BlogPost.findById(myId, function (err, post) {
  if (!err) {
    post.comments[0].remove();
    post.save(function (err) {
      // do something
    });
  }
});
```
**Example:**

```javascript
//import mongoose module
var mongoose = require('mongoose');

//connect to mongodb
mongoose.connect('mongodb://127.0.0.1:27017/test');

//checking connection with mongodb
var db = mongoose.connection;
db.on('error', console.error.bind(console, 'connection error:'));

db.on('open', function(err) {
	console.log('database connected');
});

//Defining schema
var Schema = mongoose.Schema;

var userData = new Schema({
	name: {type: String},
	address: String,
	mob: String,
	dob : {type: Date, default: Date.now}
});

userData.methods.printName = function() {
	console.log('my name is : '+this.name);
};

var newModel = mongoose.model('users', userData);
var newModel1 = new newModel({name : "hhhhh"});
newModel1.printName();

var user = new newModel({
	name: "Hotam",
	address: "Agra",
	mob: "9856234710",
	dob : '15/04/1991'
	
});

newModel.find({}, function(err, docs) {
	if(err) {
		console.log('data not found error : '+ err)
		throw err;
	}else if(docs.length) {
		console.log('user data : '+docs);
	}else {
		user.save(function(err) {
			if(err) {
				console.log('error : '+err);
				throw err;
			}
			console.log('user data is saved');
		});
	}
});
```

## bluebird
## q
## moment
## fs
## winston

### Instantiating your own Logger

```javascript
var logger = new winston.Logger({
    transports: [
        new (winston.transports.Console)(),     //It will display the log on console
        new (winston.transports.File)({ filename: 'logs/winston_own.log' })      //It will display log in a file named winston_own.log
    ]
});
logger.remove(winston.transports.Console);      //It will remove console transport to write logs on the console
logger.log('info', 'Hello distributed log files!');
logger.info('Hello again distributed logs');
```

**Example**
```javascript
//import winston module
var winston = require('winston')

//Define custom log levels and colors
const myCustomLevels = {
  levels: {
    foo: 0,
    bar: 1,
    baz: 2,
    foobar: 3
  },
  colors: {
    foo: 'blue',
    bar: 'green',
    baz: 'yellow',
    foobar: 'red'
  }
};

//custom logger
const customLevelLogger = new (winston.Logger)({
  level: 'foobar',
  levels: myCustomLevels.levels,
  transports: [
    new winston.transports.Console()
  ]
});

customLevelLogger.foobar('some foobar level-ed message');
customLevelLogger.baz('some baz level-ed message');
customLevelLogger.bar('some bar level-ed message');
customLevelLogger.foo('some foo level-ed message');
```

### Add/Remove transport

```javascript
//By default, only the Console transport is set on the default logger. 
//You can add or remove transports via the add() and remove() methods:

winston.add(winston.transports.File, { filename: 'logs/winston_default.log' });      //It will write log into a file named winston_default.log
winston.remove(winston.transports.Console);     //It will enable console not to display log message on console.
```
### Daily rotate your log file
```javascript
require('winston-daily-rotate-file');
var options = {
    filename: 'logs/./log',
    datePattern: 'yyyy-MM-dd.',
    prepend: true,
    json: false,
    handleExceptions: true,     //if true, Catch Unhandled Exceptions
    humanReadableUnhandledException: true,      //Unhandled Exceptions in more redable form
    level: process.env.ENV === 'development' ? 'debug' : 'info',
    exitOnError: false      //By default winston will exit if any uncaught exception occurrs. Set this option to false to work winston properly.
}
var transport = new winston.transports.DailyRotateFile(options)
var dailyLogger = new winston.Logger({
    transports: [
        transport
    ]
});

dailyLogger.log('info', 'Hello distributed log files!');
dailyLogger.info('Hello again distributed logs');
```

**Example**

```javascript
var winston = require('winston');
require('winston-daily-rotate-file');

var transport = new (winston.transports.DailyRotateFile)({
  filename: './log',
  datePattern: 'yyyy-MM-dd.',
  prepend: true,
  json: false,
  level: process.env.ENV === 'development' ? 'debug' : 'info'
});

var errorTransport = new (winston.transports.DailyRotateFile)({
    filename: '_ERROR./log',
    datePattern: 'yyyy-MM-dd.',
    prepend: true,
    json: false,
    level: process.env.ENV === 'development' ? 'debug' : 'error'
  });

var logger = new (winston.Logger)({
  transports: [
    transport,
    errorTransport
  ]
});

module.exports = logger;
```
### Multiple transports of the same type

```javascript
var multipleTransportsLogger = new winston.Logger({
  transports: [
    new (winston.transports.File)({
      name: 'info-file',
      filename: 'logs/filelog_info.log',
      level: 'info'
    }),
    new (winston.transports.File)({
      name: 'error-file',
      filename: 'logs/filelog_error.log',
      level: 'error'
    }),
  ],
  exceptionHandlers: [
    new winston.transports.File({ filename: 'logs/exceptions.log' })
  ]
});

multipleTransportsLogger.log('info', 'Hello distributed log files!');
multipleTransportsLogger.log('error', 'Hello again distributed logs');
```

### Exception Handler using winston
```javascript
var winston = require('winston');

var logger = new (winston.Logger)({
  transports: [
    new (winston.transports.Console)({ json: false, timestamp: true }),  // logs printed on console
    new winston.transports.File({ filename: __dirname + '/debug.log', json: false })  // logs printed on debug.log file
  ],
  exceptionHandlers: [
    new (winston.transports.Console)({ json: false, timestamp: true }), // logs printed on console
    new winston.transports.File({ filename: __dirname + '/exceptions.log', json: false })  // logs printed on exceptions.log file
  ],
  exitOnError: false // if true, it will exit on an erorr
});

module.exports = logger;
```

### Add colors to custom logger
```javascript
var winston = require('winston');
var myCustomLevels = {
    levels: {
        info: 0,
        error: 1,
        warn: 2
    },
    colors: {
        info: 'red',
        error: 'green',
        warn: 'yellow'
    }
};

var transport = new (winston.transports.Console)({
    levels: myCustomLevels.levels,
    prettyPrint: false,
    colorize: true,
    silent: false,
    timestamp: false
});

var fileTransport = new (winston.transports.File)({
    levels: myCustomLevels.levels,
    filename: 'logs/custom_file_logger.log',
    prepend: true,
    json: false,
    prettyPrint: false,
    colorize: true,
    silent: false,
    timestamp: false
});

winston.addColors(myCustomLevels.colors);
var customLogger = new winston.Logger({
    transports: [
        transport,
        fileTransport
    ]
});


customLogger.info('I will be printed in red color');
customLogger.error('I will be printed in green color');
customLogger.warn('I will be printed in yellow color');
```

## swagger

### Set up to application
```javascript
var subpath = express();
var swagger = require("swagger-node-express");
app.use("/v1", subpath);
swagger.setAppHandler(subpath);
subpath.use(express.static('dist'));
swagger.setApiInfo({
    title: "example API",
    description: "API to do something, manage something...",
    termsOfServiceUrl: "",
    contact: "hotam.singh@oodlestechnologies.com",
    license: "",
    licenseUrl: ""
});
subpath.get('/', function (req, res) {
    res.sendFile(__dirname + '/dist/index.html');
});
swagger.configureSwaggerPaths('', 'api-docs', '');
var domain = scope.config.swaggerDomain || 'localhost';
var applicationUrl = 'http://' + domain;
swagger.configure(applicationUrl, '1.0.0');
```
## redis
Redis is a fast and efficient in-memory key-value store. It is also known as a data structure server, as the keys can contain strings, lists, sets, hashes and other data structures.

### Installation
```
npm install redis
```

### Getting Started
Once you have installed node_redis module you are good to go. Let’s create a simple file, `app.js`, and see how to connect with Redis from Node.js.

app.js

```javascript


var redis = require('redis');
var client = redis.createClient(); //creates a new client
```
By default, `redis.createClient()` will use `127.0.0.1` and `6379` as the hostname and port respectively. If you have a different `host/port` you can supply them as following:
```javascript
var client = redis.createClient(port, host);
```
### Storing Key-Value Pairs
#### Storing Strings:
All the Redis commands are exposed as different functions on the client object. To store a simple string use the following syntax:
```javascript
client.set('framework', 'AngularJS');
```
Or
```javascript
client.set(['framework', 'AngularJS']);
```
You can also pass an optional callback to get a notification when the operation is complete:
```javascript
client.set('framework', 'AngularJS', function(err, reply) {
  console.log(reply);
});
```

If the operation failed for some reason, the `err` argument to the callback represents the error. To retrieve the value of the key do the following:
```javascript
client.get('framework', function(err, reply) {
    console.log(reply); //null if not exists
});
```

`client.get()` lets you retrieve a key stored in Redis. The value of the key can be accessed via the callback argument reply. If the key doesn’t exist, the value of reply will be empty.

#### Storing Hash:

Many times storing simple values won’t solve your problem. You will need to store hashes (objects) in Redis. For that you can use `hmset()` function as following:

```javascript
client.hmset('frameworks', 'javascript', 'AngularJS', 'css', 'Bootstrap', 'node', 'Express');

client.hgetall('frameworks', function(err, object) {
    console.log(object);
});
```

The above snippet stores a `hash` in Redis that maps each technology to its framework. The first argument to `hmset()` is the name of the key. Subsequent arguments represent key-value pairs. Similarly, `hgetall()` is used to retrieve the value of the key. If the key is found, the second argument to the callback will contain the value which is an object.

**Note:** - Redis doesn’t support nested objects. All the property values in the object will be coerced into strings before getting stored.

You can also use the following syntax to store objects in Redis:
```javascript
client.hmset('frameworks', {
    'javascript': 'AngularJS',
    'css': 'Bootstrap',
    'node': 'Express'
});
```

#### Storing Sets:
Sets are similar to lists, but the difference is that they don’t allow duplicates. So, if you don’t want any duplicate elements in your list you can use a set.

```javascript
client.sadd(['tags', 'angularjs', 'backbonejs', 'emberjs'], function(err, reply) {
    console.log(reply); // 3
});
```
As you can see, the `sadd()` function creates a new set with the specified elements. Here, the length of the set is three. To retrieve the members of the set, use the `smembers()` function as following:

```javascript
client.smembers('tags', function(err, reply) {
    console.log(reply);
});
```

This snippet will retrieve all the members of the set. Just note that the order is not preserved while retrieving the members.

### Checking the Existence of Keys
Sometimes you may need to check if a key already exists and proceed accordingly. To do so you can use `exists()` function as shown below:
```javascript
client.exists('key', function(err, reply) {
    if (reply === 1) {
        console.log('exists');
    } else {
        console.log('doesn\'t exist');
    }
});
```

### Deleting a Key
At times you will need to clear some keys and reinitialize them. To clear the keys, you can use del command as shown below:

```javascript
client.del('frameworks', function(err, reply) {
    console.log(reply); //returns 1 if successfull otherwise 0
});
```
### Expire a Key
You can also give an expiration time to an existing key as following:
```javascript
client.set('key1', 'val1');
client.expire('key1', 30); //this key will automatically expire in 30 seconds
```

## handlebars
## ejs
## dotenv
## jsonwebtoken
## cors
## commander
## node-cron
**Example: Run cron job every minute**
```javascript
var cron = require('node-cron');
cron.schedule('* * * * *', function () { // * * * * * runs cron job every minute
    var dbTables = [
        'blocks',
        'dapps',
        'delegates',
        'mem_accounts',
        'migrations',
        'rounds_fees',
        'trs',
        'votes',
        'signatures',
        'stake_orders',
        'peers',
        'peers_dapp',
        'intransfer',
        'outtransfer',
        'multisignatures'
    ];
    dbTables.forEach(function (tableName) {
        scope.db.query('SELECT * FROM ' + tableName)
            .then(function (rows) {
                if (rows.length > 0) {
                    var bulk = utils.makeBulk(rows, tableName);
                    utils.indexall(bulk, tableName)
                        .then(function (result) {
                            //Handle further operation in case of successfull indexing if needed
                        })
                        .catch(function (err) {
                            console.log('elasticsearch error : ', err);
                        });
                }
            })
            .catch(function (err) {
                console.log('database error : ', err);
            });
    });
});
```
## appmetrics

**Example: Monitor app using appmetrics**
```javascript
var appmetrics = require('appmetrics');
var monitoring = appmetrics.monitor();

const chalk = require('chalk');
 
var http = require('http');
 
const port = 3800;

const pg = require('pg-promise')({});
const connectionString = process.env.DATABASE_URL || 'postgres://localhost:5432/lisk_main';
const client = pg(connectionString);
//const client = new pg.Client(connectionString);
client.connect();
//const query = client.query('CREATE TABLE items(id SERIAL PRIMARY KEY, text VARCHAR(40) not null, complete BOOLEAN)');

  client.query('select * from items', function(err, data) {
      if(err) {
          console.log('error : '+err);
      }
      else {
          console.log('data : '+data);
      }
  });
//query.on('end', () => { client.end(); });

monitoring.on('initialized', function (env) {
    console.log(chalk.yellow('[ETPCoinMetric] init'));
});
monitoring.on('http', function (data) {
    console.log(chalk.yellow('[ETPCoinMetric] duration='+data.duration+' ms url='+data.url));
});
monitoring.on('postgres', function (data) {
    console.log(chalk.yellow('[ETPCoinMetric] duration='+data.duration+' ms query='+JSON.stringify(data.query)));
});
 
const requestHandler = (request, response) => {  
  response.end('Hello')
}
 
const server = http.createServer(requestHandler);
 
server.listen(port, (err) => {  
  if (err) {
    return console.log('An error occurred', err)
  }
  console.log(`Server is listening on ${port}`)
});
```
## NodeJS Questions And Answers

### How to process an array using async/await?
```javascript
var Promise = require('bluebird');

async function processArray(arr) {
    await Promise.all(arr.map(async function(tableName) {
        console.log(tableName);
    }));
}

processArray([1, 2, 3, 4, 5]);
```

### How to detect device type in nodejs?
```javascript
'use strict';

var express = require('express');
var device = require('express-device');
var app = express();
app.use(device.capture());

app.get('/api/device', function(req, res) {
    res.send('device : ' + req.device.type.toUpperCase());
});

app.listen('8081', function() {
    console.log('server started on port : 8081');
});
```

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
Or if you have already cloned the project, you can use:
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
# Important Commands

## Linux Commands

### check ubuntu version
`$ lsb_release -a`

### Change password for a user in ubuntu
`$ passwd`

### access to the root directories
```
$ sudo -H /bin/bash 
$ cd /etc/apt
do your editing of files
exit
```
### create a soft link
`$ sudo ln -fs /home/hotam/project/git/QA-automation /etc/automation`

### Check Permissions For A Directory or File in linux
`$ ls -la /root or <any directory here>`

### edit `/etc/environment` directory
`$ sudo -H gedit /etc/environment`

### create hard link in linux
`$ ln {source} {link}`

### Enable wifi
`$ sudo service network-manager restart`

### get wi-fi configuration
`$ iwconfig`

### Get all info and cause of issue in a txt file.
`$ wget -N -t 5 -T 10 https://github.com/UbuntuForums/wireless-info/raw/master/wireless-info && chmod +x wireless-info && ./wireless-info`

### BIOS status for bluetooth and wi-fi
```
$ rfkill list
$ sudo rfkill unblock all
```

### Install cryptkeeper on ubuntu
```
$ sudo apt-get update
$ sudo apt-get install cryptkeeper
```

## GitHub Commands

### Fiest commit on GitHub
```
$ echo "# elasticsearch_with_node" >> README.md
$ git init
$ git add .
$ git add README.md //optional
$ git commit -m "first commit"
$ git remote add origin https://github.com/hotam-singh/<repository_name>.git
$ git push -u origin master
```
### Ignore config.json before commiting.
```
$ git update-index --assume-unchanged <file>

//Example:
$ git update-index --assume-unchanged config.json
```
###  Re-commit config.json before commiting.
```
$ git update-index --no-assume-unchanged <file>

//Example:
$ git update-index --no-assume-unchanged config.json
```
### Check Permissions For A Directory or File in linux
```
ls -la /root
```
## NodeJS Commands

### install node.js in ubuntu
```
$ sudo apt-get update
$ sudo apt-get install nodejs
$ nodejs -v
```

### install npm in ubuntu
```
$ sudo apt-get install npm
$ npm -v
```

### replace nodejs with node
```
$ ln -s /usr/bin/nodejs /usr/bin/node OR sudo ln -s /usr/bin/nodejs /usr/bin/node
$ nodejs -v
$ node -v
```

### upgrade node to the latest version
```
$ sudo npm cache clean -f
$ sudo npm install -g n
$ sudo n stable
$ node -v
```

### Updating node modules inside package.json
```
$ sudo npm install -g npm-check-updates
$ ncu
$ ncu –u
$ npm install
```

### Stop running process
```
$ killall node
$ ps -ef|grep node
```

### To get any application already running on specific port which we are trying to connect to
`$ sudo lsof -i -P -n | grep LISTEN`

### Killing Node Process Running In Backend solution: 1
`$ pkill -f node`

### Killing Node Process Running In Backend solution: 2
```
$ ps aux | grep node
$ kill -9 process_id
```

## NPM Commands

### update npm to latest version 
`$ sudo npm i -g npm`

## MySQL Commands

### Install mysql on ubuntu
```
$ sudo apt-get update
$ sudo apt-get install mysql-server

// Run security script. It will allow you to set default security settings.
$ mysql_secure_installation
```

### connect to mysql database
`$ mysql -u root -p`

### change mysql password if forgot
```
$ sudo /etc/init.d/mysql stop
$ sudo mysqld --skip-grant-tables & mysql -u root mysql
$ UPDATE mysql.user SET Password=PASSWORD('YOURNEWPASSWORD') WHERE User='root'; FLUSH PRIVILEGES; exit;
```

### To verify my mysql installed or not on ubuntu
`$ dpkg --get-selections | grep mysql`

### run mysql on beta server
`$ mysql -hbetadb.websitetoolbox.com -uhotam -p`

### Check version of MYSQL
`$ SELECT VERSION(); after login into mysql shell`

### dump data from database
```
$ mysqldump -h <hostname> -u <user> --password=<password> <databasename> > filename.sql   in your terminal
Example:
$ mysqldump -h localhost -u root --password=902819 test > test.sql
```
### dump data into database
```
$ mysqldump -h <hostname> -u <user> --password=<password> <databasename> < filename.sql   in your terminal
Example:
$ mysqldump -h localhost -u root --password=902819 test < test.sql
```

### create database
`$ create database <database_namee>;`


### drop database
`$ drop database <datanase_name>;`

## PostgresQL Commands

### postgres database commands
```
$ sudo service postgresql restart
$ dropdb ETP_test
$ createdb ETP_test
$ sudo -u postgres psql -d ETP_test -c "alter user "$USER" with password 'password';"
```

### Running postgres database 
```
$ sudo -u postgres psql
$ \list or \l      //List all databases
$ \connect database_name or \c databse_name     //Connect to listed databases
$ \dt     //List Database Tables
```

### Creating dump file of existing data in postgres
`$ pg_dump -U $USER -W -d database_name > ETPDump_file  //-W=password, -d=dump`

### Create dump file of existing database schema in pstgres
`$ pg_dump -U $USER -W -Cs ETP_test > ETPDump  //-W=password -Cs=create schema`

### Back up single table from a database
`$ pg_dump --host localhost --port 5432 -U $USER --format plain --verbose --file "file_name_here" --table public.<table_name_here> <database_name_here>`

### Check version of PostgreSQL
`SELECT VERSION(); after login into postgres shell`

### dump data into database
```
$ psql <database_name> < filename
Example:
$ psql dump < psqldump
```

### dump data from database
```
$ pg_dump <database_name> > filename
Example:
$ pg_dump puppies > psqldump
```

## MongoDB Commands
 	
### check mongodb version
In mongo shell:

`db.version()`

### dump data to mongodb
`$ mongoimport -d <database name> -c <collection name> --type <file type> <path to a file> --headerline`

### dump database from mongodb
`$ mongoexport --db <datanase_name> --collection <collection_name> --out filename.json/filename.csv`

## Elasticsearch Commands

### Elastic Search server Configuration on production server
```
//After installation process, run below command to give permissions to elasticsearch directory
$ sudo chown -R elasticsearch:elasticsearch /var/lib/elasticsearch/
```

### Edit configuration of elasticsearch
```
//etc/elasticsearch/elasticsearch.yml file
$ sudo nano /etc/elasticsearch/elasticsearch.yml
```

### Restart elastic search server when any modification is made in /etc/elasticsearrch/elasticsearch.yml
```
$ sudo service elasticsearch restart
$ sudo /etc/init.d/elasticsearch start
```

### Get the status of elasticsearch server status
```
$ sudo service elasticsearch status 
// OR 
$ curl -X GET 'http://<server_ip_address>:9200'
```



	1. [JavaScript](#javascript)
    2. [NodeJS](#nodejs)
       * [Introduction](#introduction)
       * [Installation](#installation)
    3. [MongoDB](#mongodb)
    4. [AngularJS](#angularjs)
    5. [MySQL](#mysql)
    6. [PostgreSQL](#postgresql)
    7. [Elasticsearch](#Elasticsearch)
    8. [NodeJS With MongoDB](#nodejs-with-mongodb)
    9. [NodeJS With MySQL](#nodejs-with-mysql)
 
3. [Questions And Answers](#questions-and-answers)    
	1. [JavaScript Questions And Answers](#javascript-questions-and-answers)
    2. [NodeJS Questions And Answers](#nodejs-questions-and-answers)
    3. [MongoDB Questions And Answers](#mongodb-questions-and-answers)
    4. [AngularJS Questions And Answers](#angularjs-questions-and-answers)
    5. [MySQL Questions And Answers](#mysql-questions-and-answers)
    6. [PostgreSQL Questions And Answers](#postgresql-questions-and-answers)
    7. [Elasticsearch Questions And Answers](#elasticsearch-questions-and-answers)
4. [Important Commands](#important-commands)
	1. [Linux Commands](#linux-commands)
 	2. [GitHub Commands](#github-commands)
    3. [NodeJS Commands](#nodejs-commands)
    4. [NPM Commands](#npm-commands)
    5. [MySQL Commands](#mysal-commands)
    6. [PostgresQL Commands](#postgresql-commands)
    7. [MongoDB Commands](#mongodb-commands)
    8. [Elasticsearch Commands](#elasticsearch-commands)



## MongoDB

### What is mongoDB?
MongoDB is an open source document database that provides `high performance`, `high availability` and `automatic scaling`. Document database is a data structure composed of `key` and `value` pairs. MongoDB documents are similar to `JSON` objects.

![BSON Docement](https://github.com/hotam-singh/tutorials/blob/master/images/mongo1.png)

### What do you understand by NoSQL databases?
NoSQL is a type of database that can handle and sort all type of unstructured, messy and complicated data. It is just a new way to think about database.

### Which are the different languages supported by MongoDB?
MongoDB provides official driver support for C, C++, C#, Java, Node.js, Perl, PHP, Python, Ruby, Scala, Go and Erlang.

### What are the different types of NoSQL databases? Give some example.
NoSQL database can be classified as 4 basic types:

1. Key value store NoSQL database
2. Document store NoSQL database
3. Column store NoSQL database
4. Graph base NoSQL databse

### What is the difference between MongoDB and MySQL?
MongoDB and MySQL can be compared with the following terms

| Area Of Comparison | MongoDB | MySQL |
| ------------------ |:-------:| -----:|
| Data Representation | BSON | Tables |
| Query | Object Oriented | SQL |
| JOIN | Does not support | Supports |
| Automatic Transaction |Does not support | Supports |
| Schema Definition | You are not responsible for defining schema | This is your responsible to definine schema |
|Performance | It is better than MySQL | It is slower than MongoDB |
| Easy for Programmers | Yes | No |
| Complex Transactions | No | Yes |
| Auto-Sharding | Yes | No |

### Why MongoDB is known as best NoSQL database?
MongoDb is the best NoSQL database because, it:

1. is `Document Oriented`
2. Supports `Rich Query language`
3. provides `High Performance`
4. is `Highly Available`(Replica sets provide high availability using automatic failover. Failover allows a secondary member to become primary if the current primary becomes unavailable.)
5. is `Easily Scalable`

### Can you achieve primary key - foreign key relationships in MongoDB?
We can achieve primary-foreign key relationship by embedding one document inside another. **For example:** An address document can be embedded inside customer document.

### What are Indexes in MongoDB?
In MondoDB, Indexes are used to execute query efficiently. Without indexes, MongoDB must perform a collection scan, i.e. scan every document in a collection, to select those documents that match the query statement. If an appropriate index exists for a query, MongoDB can use the index to limit the number of documents it must inspect

### What is aggregation?
Aggregation is like an operation that groups values from multiple documents together, and can perform a variety of operations on the grouped data to return a single result.

MongoDB provides three ways to perform aggregation: 

1. aggregation pipeline
2. map-reduce function
3. single purpose aggregation methods

#### Aggregation Pipeline: 
The aggregation pipeline is a framework for data aggregation modeled on the concept of data processing pipelines. Documents enter a multi-stage pipeline that transforms the documents into aggregated results.

![Aggregation Example](https://github.com/hotam-singh/tutorials/blob/master/images/mongo2.png)

#### Map-Reduce:
MongoDB also provides map-reduce operations to perform aggregation. In general, map-reduce operations have two phases: a map stage that processes each document and emits one or more objects for each input document, and reduce phase that combines the output of the map operation. Optionally, map-reduce can have a finalize stage to make final modifications to the result. Like other aggregation operations, map-reduce can specify a query condition to select the input documents as well as sort and limit the results.

Map-reduce uses custom JavaScript functions to perform the map and reduce operations, as well as the optional finalize operation. While the custom JavaScript provide great flexibility compared to the aggregation pipeline, in general, map-reduce is less efficient and more complex than the aggregation pipeline.

Map-reduce can operate on a sharded collection. Map reduce operations can also output to a sharded collection. See Aggregation Pipeline and Sharded Collections and Map-Reduce and Sharded Collections for details.

![Map Reduce Example](https://github.com/hotam-singh/tutorials/blob/master/images/mongo3.png)

#### Single Purpose Aggregation Operations:
MongoDB also provides `db.collection.count()` and `db.collection.distinct()`

![Single Purpose Aggregation](https://github.com/hotam-singh/tutorials/blob/master/images/mongo4.png)

**Aggregation Example:**
```javascript
var mongodb = require('mongodb');
var mongoClient = mongodb.MongoClient;
mongoClient.connect('mongodb://127.0.0.1:27017/test', function(err, db) {
        if(err) {
                console.log('error : '+err);
                throw err;
        }
        db.collection('employees').find({}).toArray(function(err, data) {
                console.log('length : '+data.length);
                if(err) {
                        console.log('error : '+err);
                        throw err;
                }
                if(data.length > 0) {
                        db.collection('employees').aggregate([
                                {
                                        $group: {
                                                "_id": "$name",
                                                "total": {
                                                        $sum: '$salary'
                                                }
                                        }
                                }
                        ], function(err, result) {
                                console.log('aggregation result : '+JSON.stringify(result));
                        });
                }else {
                        console.log('collection doesnt have any documents. Please insert documents');
                }
        });
});
```

### What is sharding in MongoDB?
In MongoDB, Sharding is a procedure of storing data records across multiple machines. It is a MongoDB approach to meet the demands of data growth. It creates horizontal partition of data in a database or search engine. Each partition is referred as shard or database shard.

### What is replica set in MongoDB?
A replica can be specified as a group of mongo instances that host the same data set. In a replica set, one node is primary, and another is secondary. All data is replicated from primary to secondary nodes.

### What is primary and secondary replica set in MongoDB?
In MongoDB

* primary nodes are the node that can accept write. These are also known as master nodes. The replication in MongoDB is single master so, only one node can accept write operations at a time.
* Secondary nodes are known as slave nodes. These are read only nodes that replicate from the primary.

### Which are the storage engines used by MongoDB?
`MMAPv1` and `WiredTiger` are two storage engine used by MongoDB

### SQL to Aggregation mapping chart?

![SQL to Aggregation mapping chart](https://github.com/hotam-singh/tutorials/blob/master/images/mongo5.png)

**Count Example:**
![Count Example](https://github.com/hotam-singh/tutorials/blob/master/images/mongo6.png)

**Sum Example:**
![Sum Example](https://github.com/hotam-singh/tutorials/blob/master/images/mongo7.png)

**Groupby and Orderby Example:**
![Groupby and Orderby Example](https://github.com/hotam-singh/tutorials/blob/master/images/mongo8.png)
![Groupby and Orderby Example](https://github.com/hotam-singh/tutorials/blob/master/images/mongo9.png)

## AngularJS

What is a service?

* It provides us method to keep data across the lifetime of the angular app
* It provides us method to communicate data across the controllers in a consistent way
* This is a singleton object and it gets instantiated only once per application
* It is used to organize and share data and functions across the application

Angular only creates instance of a service when an application component depends on it. Keep in mind that services are singleton object and gets instantiated once per angular app using the `$injector` and they gets created when angular app components need them.

**Example:**

service to find square of a number:
```javascript
var CalculatorService = angular.module('CalculatorService', [])
.service('Calculator', function () {
	this.square = function (a) { return a*a};
});
```

An AngularJS service can be created or registered or created using the following different ways:

* Using the service() method
* Using the factory() method
* Using the provider() method
* Using the value() method
* Using the constant() method

### What are directives?

#### ng-src:
**Example:**

index.html:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>NG-SRC Demo</title>
    <script src="./angular.min.js"></script>
    <script src="./angular-route.js"></script>
    <script src="./script.js"></script>
</head>
<body ng-app="myApp">
    <div ng-controller="myController">
        <div>
            <h2><label>Name:</label>{{ country.name }}</h2>
        </div>
        <div>
            <h2><label>Capital:</label>{{ country.capital }}</h2>
        </div>
        <div>
            <img ng-src="{{ country.flag }}" alt="Indian Flag" heigth="200px;" width="400px;" />
        </div>
        
    </div>
</body>
</html>
```
script.js:
```javascript
var myApp = angular.module('myApp', [])

.controller('myController', function($scope) {
    $scope.country = {
        name: "India",
        capital: "New Delhi",
        flag: "./indian_flag.png"
    };
});
```

## MySQL

## PostgreSQL

### What is PostgreSQL?
PostgreSQL is an open-source, object-relational database management system (ORDBMS).

PostgreSQL is developed by the `PostgreSQL Global Development Group`.

It is released under the PostgreSQL License, which is an MIT-style license, 
and thus free and open source software.

PostgreSQL features highlights?

* User-defined types
* Table inheritance
* Sophisticated locking mechanism
* Foreign key referential integrity
* Nested transactions (savepoints)
* Multi-version concurrency control (MVCC)
* Asynchronous replication

The recent versions of PostgreSQL support the following features:

* Native Microsoft Windows Server version
* Tablespaces
* Point-in-time recovery

## NodeJS with MongoDB
### What are efficient ways to use mongodb in nodejs application?
* Use global instance of db
```javascript
var db =  mongodb.connect('MongoDB connection URL'); 
var app = express();
app.set('db', db);
```
* Attach db using middleware
```javascript
var db =  mongodb.connect('MongoDB connection URL');
app.use(function(req, res, next) {
	req.db = db;
})
```
* Reuse db object created by MongoClient.connect()
```javascript
use this line in a module where required:
MongoClient.connect('MongoDB connection URL')
```

## NodeJS With MySQL 

### How can I prevent SQL injection Node.JS?
We can prevent sql-injection by parameter binding:

**Example:**
```javascript
var userId = 5; 
connection.query("SELECT * FROM table WHERE userid = '" + userId + "'", function(error) { 
	if (error) throw error; 
});

//We can modify above query as:
var userId = 5; 
var sql =  'SELECT * FROM users WHERE id = ?';
var query = connection.query(sql, [userId], function(err, results) { //query.sql returns SELECT * FROM users WHERE id = '5' 
	if (err) throw error;
});
```


# Questions And Answers

## JavaScript Questions And Answers

### How to delete existing directory recursively?
```javascript
//path is the reference to a directory
removeDir.deleteFolderRecursive = function(path) {
	if( fs.existsSync(path) ) {
		fs.readdirSync(path).forEach(function(file,index){
			var curPath = path + "/" + file;
			if(fs.lstatSync(curPath).isDirectory()) { 
				// recurse
				removeDir.deleteFolderRecursive(curPath);
			} else { 
				// delete file
				console.log('deleting file : '+curPath);
				fs.unlinkSync(curPath);
			}
		});
		console.log('deleting directory : '+path);
		fs.rmdirSync(path);
	}
};
```

### How to use async/await in an array?
**Example:**
```javascript
(async function(tableArray) {
	await Promise.all(arr.map(async function (tableName) {
		scope.db.query('SELECT * FROM ' + tableName)
		.then(function (rows) {
			if (rows.length > 0) {
				var bulk = utils.makeBulk(rows, tableName);
				utils.indexall(bulk, tableName)
				.then(function(result) {
					console.log('success: ', result);
				})
				.catch(function(err) {
					console.log('err : ', err);
				})
			}
		})
		.catch(function(err) {
			console.log('err : ', err);
		});
	}));
})(tables);
```

### Convert a Unix timestamp to time in JavaScript?

**Example 1:**
```javascript
function getDateTimeFromTimestamp(unixTimeStamp) {
    var date = new Date(unixTimeStamp);
    return ('0' + date.getDate()).slice(-2) + '/' + ('0' + (date.getMonth() + 1)).slice(-2) + '/' + date.getFullYear() + ' ' + ('0' + date.getHours()).slice(-2) + ':' + ('0' + date.getMinutes()).slice(-2);
  }

var myTime = getDateTimeFromTimestamp(1435986900000);
console.log(myTime);
```
**Example 2:**

```javascript
// Create a new JavaScript Date object based on the timestamp
// multiplied by 1000 so that the argument is in milliseconds, not seconds.
var date = new Date(unix_timestamp*1000);
// Hours part from the timestamp
var hours = date.getHours();
// Minutes part from the timestamp
var minutes = "0" + date.getMinutes();
// Seconds part from the timestamp
var seconds = "0" + date.getSeconds();

// Will display time in 10:30:23 format
var formattedTime = hours + ':' + minutes.substr(-2) + ':' + seconds.substr(-2);
console.log(formattedTime);
```

**Example 3:**

```javascript
var timestamp = 1293683278;
var date = new Date(timestamp*1000);
var iso = date.toISOString().match(/(\d{2}:\d{2}:\d{2})/)
alert(iso[1]);

```

**Example 4:**

```javascript
var timeStamp = function(str) {
  return new Date(str.replace(/^(\d{2}\-)(\d{2}\-)(\d{4})$/,
    '$2$1$3')).getTime();
};
alert(timeStamp('27-04-2015'));

```

### Array reduce method?

**Example:**

Get the sum of the numbers in the array:
```javascript
var numbers = [65, 44, 12, 4];

function getSum(total, num) {
    return total + num;
}
function myFunction(item) {
    document.getElementById("demo").innerHTML = numbers.reduce(getSum);
}
```

**Definition:**

The `reduce()` method reduces the array to a single value and executes a provided function for each value of the array 
    (from left-to-right). 

**Syntax:**

```javascript
array.reduce(function(total, currentValue, currentIndex, arr), initialValue);
```
Where:

* **total:** (*) The initialValue, or the previously returned value of the function.
* **currentValue:** (*) The value of the current element of an array.
* **currentIndex:** The array index of the current element.
* **arr:** The array object the current element belongs to.
* **initialValue:** A value to be passed to the function as the initial value.



## MongoDB Questions And Answers

### How to plug-in own promise library in mongodb?
```javascript
//use native promise library
var mongoose = require('mongoose');
mongoose.Promise = global.Promise;

//Use bluebird promise library
var mongoose = require('mongoose');
mongoose.Promise = require('promise'); 

//Use q promise library
var mongoose = require('mongoose');
mongoose.Promise = require('q').Promise;
```

### What are the supported data types in mongodb?
The allowed SchemaTypes are:

* String
* Number
* Date
* Buffer
* Boolean
* Mixed
* ObjectId
* Array

## AngularJS Questions And Answers

### what is ng-serve?
It serves an Angular project via a development server

### AngularJs `$http.post()` does not send data to the server?

The difference is in how jQuery and AngularJS serialize and transmit the data. Fundamentally, 
the problem lies with your server language of choice being unable to understand AngularJS’s 
transmission natively. By default, jQuery transmits data using

`
Content-Type: x-www-form-urlencoded
and the familiar foo=bar&baz=moe serialization.
`

And AngularJS, however, transmits data using

`Content-Type: application/json 
and { "foo": "bar", "baz": "moe" }`

We can solve this by setting content-type as the following two ways:

**Solution 1:**

```javascript
angular.module('MyModule', [], function($httpProvider) {
	// Use x-www-form-urlencoded Content-Type
	$httpProvider.defaults.headers.post['Content-Type'] = 'application/x-www-form-urlencoded;charset=utf-8';
});

//and send $http.post() like this:
$http.post('/register', DataObject)
	.then(function(response) {
		alert('resp : ' + response);
    });
});
```
**Solution 2:**
```javascript
$http({
    method: 'POST',
    url: '/register',
    data: this.regData,
    headers: {'Content-Type': 'application/x-www-form-urlencoded'}
});
```

### Injecting a service into another service in angularJS

Yes. follow the regular injection rule in angularjs.

```javascript
//Solution 1: 
app.service('service1', function(){});
//Inject service1 into service2
app.service('service2',function(service1){});

//Solution 2:
app.service('service1', function(){});
//Inject service1 into service2
//It is better to use Array injection to avoid minifying problem.
app.service('service2',['service1', function(service1) {}]);

```

## MySQL Questions And Answers

## PostgreSQL Questions And Answers

### Install pgAdmin4 on linux 16.04?
```
$ sudo apt-get install virtualenv python-pip libpq-dev python-dev
$ cd
$ virtualenv pgadmin4
$ cd pgadmin4
$ source bin/activate
$ pip install https://ftp.postgresql.org/pub/pgadmin/pgadmin4/v2.1/pip/pgadmin4-2.1-py2.py3-none-any.whl
$ nano lib/python2.7/site-packages/pgadmin4/config_local.py
```
Paste below code:
```
import os
DATA_DIR = os.path.realpath(os.path.expanduser(u'~/.pgadmin/'))
LOG_FILE = os.path.join(DATA_DIR, 'pgadmin4.log')
SQLITE_PATH = os.path.join(DATA_DIR, 'pgadmin4.db')
SESSION_DB_PATH = os.path.join(DATA_DIR, 'sessions')
STORAGE_DIR = os.path.join(DATA_DIR, 'storage')
SERVER_MODE = False
```
and save this file. Now run:
`$ python lib/python2.7/site-packages/pgadmin4/pgAdmin4.py`

Now run:
```
$ cd ~/pgadmin4
$ source bin/activate
$ python lib/python2.7/site-packages/pgadmin4/pgAdmin4.py
```
Now you can check postgres on: `localhost:5000`

**Make a shortcut:**
```
$ touch ~/pgadmin4/pgadmin4
$ chmod +x ~/pgadmin4/pgadmin4
$ nano ~/pgadmin4/pgadmin4
```
Write below code:

```
#!/bin/bash
cd ~/pgadmin4
source bin/activate
python lib/python2.7/site-packages/pgadmin4/pgAdmin4.py

```
and save this file.

Now you can just run it with a single command:

`$ ~/pgadmin4/pgadmin4`

### How to change owner of database in postgres?
`ALTER DATABASE "database_name" OWNER TO "owner_name";`

**Example:**

`ALTER DATABASE "ETP_test" OWNER TO root;`

## Elasticsearch Questions And Answers

### How to use range query in elasticsearch?

```json
body: {
    "query": {
    	"bool": {
    		"must": [
    			{
    				"range": {
    					"startTime": {
    						"gte": startTime,
    						"lte": endTime
    					}
    				}
    			}
    		],
    		"must_not": [],
    		"should": []
    	}
    },
    "from": 0,
    "size": 10,
    "sort": [],
    "aggs": {}
}

```

### Multi-field search example in Elasticsearch?

```json
body: {
    "query": {
    	"bool": {
    		"must": [
    			{
    				"term": {
    					"status": status
    				}
    			},
    			{
    				"term": {
    					"senderId.keyword": address
    				}
    			}
    		],
    		"must_not": [],
    		"should": []
    	}
    },
    "sort": [],
    "aggs": {}
}

```


