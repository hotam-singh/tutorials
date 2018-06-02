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
