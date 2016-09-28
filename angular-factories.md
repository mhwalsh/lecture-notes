### Angular Factories

### MVC

### Services
##### Why Services? 
[https://docs.angularjs.org/guide/services](https://docs.angularjs.org/guide/services) and ng-book.

- Controllers are instantiated as needed. Every time we switch or reload a page/view the current controller is cleared. That means all of our client side state lost and regenerated.
- Keep data around for the lifetime of an app
- Share data between controllers - DRY
- Lazily Loaded
- Singleton
- encapsulation of functionality - "keep together those methods that relate to a specific function"

#### What are the types of services
Providers, Factories, Values, Constant ...
[http://angular-tips.com/blog/2013/08/understanding-service-types/](http://angular-tips.com/blog/2013/08/understanding-service-types/)

#### Why factories?
Flexible, but still complex enough that they can suit all of our use cases.

#### What are the built in services and non-core services

- ```$http``` is an example of a built in.
- ```angular-routing``` is an example of a non-core service.

#### Registering a Service and Dependency Injection
This can be done the same way as a controller. 

#### Promises
"The Promise object is used for asynchronous computations. A Promise represents a value which may be available now, or in the future, or never." [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

- it is what allows us to call .then on things
- what $http returns from our get/post calls
- async, waiting
- object acts as a proxy for a result because computation isn't complete yet 'wiki' [https://en.wikipedia.org/wiki/Futures_and_promises](https://en.wikipedia.org/wiki/Futures_and_promises)

