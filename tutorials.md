1. [Tutorials](#tutorials)
    1. [NodeJS](#nodejs)
    2. [MongoDB](#mongodb)
    3. [AngularJS](#angularjs)
    4. [MySQL](#mysql)
    5. [PostgreSQL](#postgresql)
    6. [NodeJS With MongoDB](#nodejs-with-mongodb)
    7. [NodeJS With MySQL](#nodejs-with-mysql)
2. [NodeJS Pupular Modules](#nodejs-pupular-modules)
    1. [passport](#passport)   
3. [Questions And Answers](#questions-and-answers)    
    1. [NodeJS Questions And Answers](#nodejs-questions-and-answers)
    2. [MongoDB Questions And Answers](#mongodb-questions-and-answers)
    3. [AngularJS Questions And Answers](#angularjs-questions-and-answers)
    4. [MySQL Questions And Answers](#mysql-questions-and-answers)
    5. [PostgreSQL Questions And Answers](#postgresql-questions-and-answers)
    
# Tutorials

## NodeJS

### What is nodejs?
Node.js is a javascript runtime built on chrome’s V8 engine for building fast scalable network application. Node.js uses an event driven, non-blocking I/O model that makes it lightweight and efficient. 

Node.js is basically a library and a runtime environment that allows us to execute javascript on the server.

### What is V8?
V8 is Google’s open-source high-performance javascript engine written in c++. V8 has following functionalities.

* Compiles and executes javascript source code.
* Handles memory allocation for objects.
* Garbage collects the objects if no longer needed.

**Virtual machines used by different browsers:**

* **v8** used by `Google`
* **Chakra** used by `MicroSoft`
* **SpiderMonkey** used by `Mozzila`
* **JavaScriptCore** used by `Apple`

### What is npm?
Npm stands for node package manager. It has main 2 functions.

* Online repositories for Node.js package/modules
* Command line utility to install Node.js modules, version management and dependency management.

### Why Node.js?
* No need to learn another language for server side code.
* Non-blocking
* Very Fast
* Single threaded but highly scalable.

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

![BSON Docement](https://github.com/hotam-singh/tutorials/tree/master/images/mongo1.png)

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

![Aggregation Example](https://github.com/hotam-singh/tutorials/tree/master/images/mongo2.png)

#### Map-Reduce:
MongoDB also provides map-reduce operations to perform aggregation. In general, map-reduce operations have two phases: a map stage that processes each document and emits one or more objects for each input document, and reduce phase that combines the output of the map operation. Optionally, map-reduce can have a finalize stage to make final modifications to the result. Like other aggregation operations, map-reduce can specify a query condition to select the input documents as well as sort and limit the results.

Map-reduce uses custom JavaScript functions to perform the map and reduce operations, as well as the optional finalize operation. While the custom JavaScript provide great flexibility compared to the aggregation pipeline, in general, map-reduce is less efficient and more complex than the aggregation pipeline.

Map-reduce can operate on a sharded collection. Map reduce operations can also output to a sharded collection. See Aggregation Pipeline and Sharded Collections and Map-Reduce and Sharded Collections for details.

![Map Reduce Example](https://github.com/hotam-singh/tutorials/tree/master/images/mongo3.png)

#### Single Purpose Aggregation Operations:
MongoDB also provides `db.collection.count()` and `db.collection.distinct()`

![Single Purpose Aggregation](https://github.com/hotam-singh/tutorials/tree/master/images/mongo4.png)

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

![SQL to Aggregation mapping chart](https://github.com/hotam-singh/tutorials/tree/master/images/mongo5.png)

**Count Example:**
![Count Example](https://github.com/hotam-singh/tutorials/tree/master/images/mongo6.png)

**Sum Example:**
![Sum Example](https://github.com/hotam-singh/tutorials/tree/master/images/mongo7.png)

**Groupby and Orderby Example:**
![Groupby and Orderby Example](https://github.com/hotam-singh/tutorials/tree/master/images/mongo8.png)
![Groupby and Orderby Example](https://github.com/hotam-singh/tutorials/tree/master/images/mongo9.png)

## AngularJS

## MySQL

## PostgreSQL

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

## AngularJS Questions And Answers

## MySQL Questions And Answers

## PostgreSQL Questions And Answers
