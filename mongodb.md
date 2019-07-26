# MongoDB

## 1. Overview
* open-source(It is freely available)
* cross-plateform(it can be run on different plateforms or operating environments)
* document-oriented database(stored data in BSON key/value fashion). Also known as NoSQL database.
* written in c++
* used for high volume data storage

## 2. Features
* high performance
* high availability
* automatic scaling(Setting a mirror across local and wide area networks)
* strong consistency
* sharding - If the load increases (more storage space, more processing power), can be distributed to other nodes across computer networks. This is known as sharding.
* load is balanced automatically by keeping data in shrades
* suitable for real-time analytics and processing massive amount of queries
* Embeded documents and array reduced the use of expensive joins
* Ability to run on multiple servers
* Supports MapReduce - MongoDB supports Map/Reduce framework for the batch processing of data and aggregation operation.

## 3. MongoDB VS MySQL
| Criteria	               | MongoDB	               | MySQL                     |
|------------------------------|-------------------------------|---------------------------| 
| Data Models	               | Many alternative data models  | Relational database management system |
| Architecture	               | Schema less	               | Schema                    |
| Operations	               | Supports atomicity	       |Transactional relation data store  |
| Query Language	       | JSON query	               | SQL                       |
| Performance Enhancement by   | Server-side scripting	       | Stored procedures implemented  |
| Scalability	               | Highly scale                  | Not Scalable              |
| Speed	                       | Faster	                       | Slower                    |


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

## 4. MongoDB Queries

### 4.1 insert
#### 4.1.1 db.collection.insertOne()
It can insert one document into a collection at a time.

**syntax**

**mongo shell:**
```javascript
> db.collectionName.insertOne({
        key1: value1,
        key2: value2,
        key3: value3,
        .
        .
        .
        keyn: valuen
})
```
Example1: 
```javascript
> db.testCollection.insertOne({
        "firstName": "hotam",
        "lastName": "singh",
        "age": 27
})
```
**NodeJS**
```javascript
> db.collection('collectionName').insertOne({
        key1: value1,
        key2: value2,
        key3: value3,
        .
        .
        .
        keyn: valuen
})
```
Example2:
```javascript
> db.collection('testCollection').insertOne({
        "firstName": "hotam",
        "lastName": "singh",
        "age": 27
})
```

#### 4.1.2 db.collection.insertMany()
It can insert multiple documents into a collection

**syntax in mongo shell**

```javascript
> db.collectionName.insertMany([
        {
                // document 1
        },
        {
                // document 2
        },
        {
                // document 3
        }
        .
        .
        .
        {
                // document n
        }
])
```
**Example:**
```javascript
db.inventory.insertMany([
   // MongoDB adds the _id field with an ObjectId if _id is not present
   { item: "journal", qty: 25, status: "A",
       size: { h: 14, w: 21, uom: "cm" }, tags: [ "blank", "red" ] },
   { item: "notebook", qty: 50, status: "A",
       size: { h: 8.5, w: 11, uom: "in" }, tags: [ "red", "blank" ] },
   { item: "paper", qty: 100, status: "D",
       size: { h: 8.5, w: 11, uom: "in" }, tags: [ "red", "blank", "plain" ] },
   { item: "planner", qty: 75, status: "D",
       size: { h: 22.85, w: 30, uom: "cm" }, tags: [ "blank", "red" ] },
   { item: "postcard", qty: 45, status: "A",
       size: { h: 10, w: 15.25, uom: "cm" }, tags: [ "blue" ] }
]);
```

**Syntax in NodeJS**
```javascript
db.collection('collectionName').insertMany([
        {
                // document 1
        },
        {
                // document 2
        },
        {
                // document 3
        }
        .
        .
        .
        {
                // document n
        }
])
```
**Example:**

```javascript
db.collection('inventory').insertMany([
   // MongoDB adds the _id field with an ObjectId if _id is not present
   { item: "journal", qty: 25, status: "A",
       size: { h: 14, w: 21, uom: "cm" }, tags: [ "blank", "red" ] },
   { item: "notebook", qty: 50, status: "A",
       size: { h: 8.5, w: 11, uom: "in" }, tags: [ "red", "blank" ] },
   { item: "paper", qty: 100, status: "D",
       size: { h: 8.5, w: 11, uom: "in" }, tags: [ "red", "blank", "plain" ] },
   { item: "planner", qty: 75, status: "D",
       size: { h: 22.85, w: 30, uom: "cm" }, tags: [ "blank", "red" ] },
   { item: "postcard", qty: 45, status: "A",
       size: { h: 10, w: 15.25, uom: "cm" }, tags: [ "blue" ] }
]);
```
#### 4.1.3 db.collection.insert()
It can insert one or more documents into a collection at a time. See insertOne() and insertMany() syntax to work with respectively.

#### 4.1.4 Additional Methods for Inserts
The following methods can also add new documents to a collection:

`db.collection.update()` when used with the **upsert: true** option.
`db.collection.updateOne()` when used with the **upsert: true** option.
`db.collection.updateMany()` when used with the **upsert: true** option.
`db.collection.findAndModify()` when used with the **upsert: true** option.
`db.collection.findOneAndUpdate()` when used with the **upsert: true** option.
`db.collection.findOneAndReplace()` when used with the **upsert: true** option.
`db.collection.save()`
`db.collection.bulkWrite()`

### 4.2 read
#### 4.2.1 db.collection.find(query, projection)
`query:` Optional. Specify query filter based on query operators i.e. 

`projection:` Optional. Specifies the fields to return in the documents that match the query filter

**Examples:**
```javascript
//find all documents from a collection
db.users.find()

// query for equality
1. db.users.find( { _id: 5 } )
2. db.users.find( { "name.last": "Singh" } )

//NOTE: To access fields in an embedded document, use dot notation ("<embedded document>.<field>").

//Query Using Operators
1. db.users.find(
   { _id: { $in: [ 5, ObjectId("507c35dd8fada716c89d0013") ] } }
)
2. db.bios.find( { birth: { $gt: new Date('1950-01-01') } } )
3. db.bios.find(
   { "name.last": { $regex: /^N/ } } // get all documents where field last start with letter N
)

//Query for Ranges 
db.bios.find( { birth: { $gt: new Date('1940-01-01'), $lt: new Date('1960-01-01') } } )

//Query for Multiple Conditions
db.bios.find( {
   birth: { $gt: new Date('1920-01-01') },
   death: { $exists: false }
} )

//Order Documents in the Result Set
The sort() method orders the documents in the result set. The following operation returns documents in the bios collection sorted in ascending order by the name field:

db.bios.find().sort( { name: 1 } )

//NOTE: 1- decending order and 0- assending order

// Limit the Number of Documents to Return
The limit() method limits the number of documents in the result set. The following operation returns at most 5 documents in the bios collection:

db.bios.find().limit( 5 )

// Set the Starting Point of the Result Set
The skip() method controls the starting point of the results set. The following operation skips the first 5 documents in the bios collection and returns all remaining documents:

db.bios.find().skip( 5 )

// Combine Cursor Methods
The following statements chain cursor methods limit() and sort():

db.bios.find().sort( { name: 1 } ).limit( 5 )
db.bios.find().limit( 5 ).sort( { name: 1 } )

//Specify AND Conditions
db.inventory.find( { status: "A", qty: { $lt: 30 } } )

// Specify OR condtions
db.inventory.find( { $or: [ { status: "A" }, { qty: { $lt: 30 } } ] } )

//Specify AND as well as OR Conditions
db.inventory.find( {
     status: "A",
     $or: [ { qty: { $lt: 30 } }, { item: /^p/ } ]
} )
```
### 4.3 update
`db.collection.update();`

### 4.4 delete
`db.collection.remove();`

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
