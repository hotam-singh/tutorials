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
