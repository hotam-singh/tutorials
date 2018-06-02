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