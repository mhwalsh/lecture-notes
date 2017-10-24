### Server Side Testing for Node.js with Mocha and Chai

Up until now we have been doing all manual testing. We can write code that will run these tests. These tests can happen at any layer. There are tools that can click through your app and test it fully. We are going to focus on server side testing of modules and our API.

#### What is [Mocha](http://mochajs.org/)?
JavaScript test framework for Node.js. We can use this to test our modules and basic JavaScript functionality or we can use it to test our server API.
#### What is [Chai](http://chaijs.com/)?
Assertion library that pairs with any JavaScript testing framework. 

	- show examples of assertion on the chai site. Words like "should, expect, assert"

#### Testing Jargon you may encounter
- BDD vs TDD
- Automated Tests
	- Integration Tests
	- Unit Tests


#### Resources
- [https://semaphoreci.com/community/tutorials/getting-started-with-node-js-and-mocha](https://semaphoreci.com/community/tutorials/getting-started-with-node-js-and-mocha)

#### Walk through

- show how to test modules with chai
	- describe - nested
	- it
	- simple expect statement

	```
	 // it("generic function", function() {
    //     expect(1+1).to.equal(2);
    // });
	```
	- more complex method call?
- show how to test server code with ```request```
	- don't need to do it manually
- Travis CIgit