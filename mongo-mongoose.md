Simple server-side app, to store and retrieve users from mongo db. Simplified User model.

* add git ignore
* build out the file structure a bit
* npm init --yes
* what technologies? (express, mongoose, body-parser etc?).
* npm install these: 

```
npm install body-parser mongoose express --save
```
* build up our server quick.
* connection string
* build the model
* require the model in the server file
* add a dummy get route
* add find routes
* add create
* add delete

-----

### What is Mongoose? 
mongoose is an object modeling package for Node that essentially works like an ORM (Object Relational Mapping) that you would see in other languages. And ORM takes data from a database, and “maps” it to objects that you define in your code.

Mongoose allows us to have access to the MongoDB commands for CRUD simply and easily.

To install Mongoose in your current project run the following:

```
$ npm install mongoose --save
```

Now that we have the package, we just have to grab it in our project:

```
var mongoose = require('mongoose');
```

We also have to connect to a MongoDB database (either local or hosted):

```
mongoose.connect('mongodb://localhost:27017/myappdatabase');
```

NOTE: myappdatabase is the “document store” you’re going to put the data in. This can be anything you want, without spaces. Name it something specific to your application that you’re creating. 

Mongo will toLowerCase it and pluralize it?

### Define a Model
Before we can handle CRUD operations, we will need a mongoose Model. These models are constructors that we define. They represent documents which can be saved and retrieved from our database.

Mongoose Schema The mongoose Schema is what is used to define attributes for our documents.

Mongoose Methods Methods can also be defined on a mongoose schema.