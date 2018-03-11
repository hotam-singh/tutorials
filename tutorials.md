1. [Tutorials](#tutorials)
	1. [JavaScript](#javascript)
    2. [NodeJS](#nodejs)
    3. [MongoDB](#mongodb)
    4. [AngularJS](#angularjs)
    5. [MySQL](#mysql)
    6. [PostgreSQL](#postgresql)
    7. [NodeJS With MongoDB](#nodejs-with-mongodb)
    8. [NodeJS With MySQL](#nodejs-with-mysql)
2. [NodeJS Pupular Modules](#nodejs-pupular-modules)
    1. [passport](#passport)   
3. [Questions And Answers](#questions-and-answers)    
	1. [JavaScript Questions And Answers](#javascript-questions-and-answers)
    2. [NodeJS Questions And Answers](#nodejs-questions-and-answers)
    3. [MongoDB Questions And Answers](#mongodb-questions-and-answers)
    4. [AngularJS Questions And Answers](#angularjs-questions-and-answers)
    5. [MySQL Questions And Answers](#mysql-questions-and-answers)
    6. [PostgreSQL Questions And Answers](#postgresql-questions-and-answers)
4. [Important Commands](#important-commands)
	1. [Linux Commands](#linux-commands)
 	2. [GitHub Commands](#github-commands)
    3. [NodeJS Commands](#nodejs-commands)
    4. [NPM Commands](#npm-commands)
    5. [MySQL Commands](#mysal-commands)
    6. [PostgresQL Commands](#postgresql-commands)
    7. [MongoDB Commands](#mongodb-commands)
    8. [Elasticsearch Commands](#elasticsearch-commands)
# Tutorials

## JavaScript

## NodeJS

### What is nodejs?
Node.js is a javascript runtime built on chrome’s V8 engine for building fast scalable network application. Node.js uses an event driven, non-blocking I/O model that makes it lightweight and efficient. 

Node.js is basically a library and a runtime environment that allows us to execute javascript on the server.

### What Node.js is not?
* Node.js is not a JavaScript library, but it is a platform to execute JavaScript on server side.
* Node.js programs are written in JavaScript but there is no DOM manipulation provided by Node.js.

### Who has developed Node.js?
Node.js was developed by `Ryan Dahl` and other developers working at `Joyent`. It was first released in 2009
supporting only Linux. In 2011, windows version was released.

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

### Why to use JavaScript on Server Side?
There are following reasons to use JavaScript on Server Side:

* Unified language for both front-end and back-end.
* Increase programmer productivity.
* Code reusability.
* Exchange of data using JSON.
* JavaScript with V8 engine performs faster than Php, Ruby, Python, JSP and ASP.NET.

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

### What is npm?
Npm stands for node package manager. It has main 2 functions.

* Online repositories for Node.js package/modules
* Command line utility to install Node.js modules, version management and dependency management.

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

###Explain Node.js Architecture?
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

### What is REPL Terminal?
REPL stands for Read-Eval-Print-Loop. It is an interface to run your JavaScript code and see the results.
You can access REPL by simply running node.js command prompt and simply run command `node`.

### How Node.js work?

Traditional Web Server

![Traditional Web Server](https://drive.google.com/uc?export=view&id=1MvyKGX4mFJMFdXdhqc8mPWvj-95sEESp)

Node.js Process Model:

![NodeJS Process Model](https://github.com/hotam-singh/tutorials/blob/master/images/node_2.png)

### What is Event Loop. How it works?


Node.js is a single-threaded application, but it can support concurrency via the concept of event and callbacks. These events and callbacks are handled by event loop.
Event Loop: It has main 2 functionalities

* Whatever the task `Web APIs` hands over  to event loop, It simply adds them up in the `callback queue`.
* Looks if `call stack` is free, pick task from the callback queue and puts it into call stack for execution.

![Event Loop](https://github.com/hotam-singh/tutorials/blob/master/images/node_3.png)

### What is Call Stack? 
Call Stack is only the javascript runtime on server where javascript is run.
### What is Web APIs?
Web APIs are those handlers which makes async programming possible. Web APIs are basically callbacks that return response once completed the given task.

### What is Callback Queue?
callback queue is a queue where all callbacks are queued up. Event loop process tasks from this queue.

### What is closure?
A closure is an inner function that has access to the outer function’s variables.
The closure has 3 scope chains

* First it looks in current heap memory.
* If a variable not found in current heap area, then looks in the outer function’s heap
* And finally looks global heap area.

**Example 1 :** 

![Closure Example 1](https://github.com/hotam-singh/tutorials/blob/master/images/node4.png)

**Example 2 :** 

![Closure Example 2](https://github.com/hotam-singh/tutorials/blob/master/images/node5.png)
### Types of closure?
There are two types of closures:
#### 1. Implicit Closure

![Implicit Closure](https://github.com/hotam-singh/tutorials/blob/master/images/node6.png)

#### 2. Explicit Closure

![Explicit Closure](https://github.com/hotam-singh/tutorials/blob/master/images/node7.png)

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
### What is Buffer?

### What are Stream?

### What are evets & event emitters?

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

# NodeJS Pupular Modules
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

# Questions And Answers

## JavaScript Questions And Answers

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

## NodeJS Questions And Answers
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

## MySQL Questions And Answers

## PostgreSQL Questions And Answers

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