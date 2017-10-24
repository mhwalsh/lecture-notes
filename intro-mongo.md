##Intro to Mongo


#### Reminder: Data Persistence
Remember back to Monday of last week... 

1. What is the value of Data Persistence?/What have you been able to do using a database that you were not able to do before?
2. What were the two types of databases that we talked about? 
3. What do people remember about the differences between these forms of databases?

-----

#### MongoDB
[https://docs.mongodb.com/manual/](https://docs.mongodb.com/manual/)

No SQL means, no tables. Show a snippet of mongo document syntax. What does this remind you of?

[https://github.com/mulchy/prime_mongo_cli_00/blob/master/bios.js](https://github.com/mulchy/prime_mongo_cli_00/blob/master/bios.js)
[https://docs.mongodb.com/manual/core/document/](https://docs.mongodb.com/manual/core/document/)

* No tables
* JSON like documents - BSON
	* pairs well with Node.js
	* MEAN stack
* dynamic schemas - _With traditional relational databases, you must define your schema before you can add any data. This inflexibility means you can’t change your schema as your data, application requirements or business evolves._
* high performance
* availability - it has a replication model
* scalability - it can scale horizontally by sharding data across multiple servers

##### Documents
BSON - binary JSON
field:value

##### Collections
A collection is a group of documents that share a purpose. 

-----
#### How to install?

To install MongoDB, first update homebrew:

```
$: brew update
```
Then install mongodb:

```
$: brew install mongodb
```

Next, you have to create the data directory used by MongoDB:
```
$: mkdir -p /data/db
```
If this throws any permissions errors, use sudo:
```
$: sudo mkdir -p /data/db
```
If you created the directory with sudo, you will need to change permissions of that file with the following commands: 

```
$: sudo chmod 0755 /data/db 
$: sudo chown -R $USER /data/db
```
Run the database with:

```
$: mongod
```

You can use brew services to manage this process too. 

```
$: brew services start mongodb
```
-----

#### Mongo Shell and AdminMongo
Two tools to interact with mongodb.

1. Any guesses to what these tools look like?

##### Mongo Shell
```
$: mongo
MongoDB shell version: 3.2.4
connecting to: test
```

##### Admin Mongo
UI/GUI tool for interacting with mongo db. It's a node project! Installation instructions:
	
[https://github.com/mrvautin/adminMongo](https://github.com/mrvautin/adminMongo)

##### RoboMongo

[https://robomongo.org/download](https://robomongo.org/download)

-----
#### Basic CRUD
How would we model our users data from first SQL lecture?

```
> show dbs
```

```
> use <database name>
```
Note: doesn't show up until you store something into it.

##### Create a collection
```
> db.createCollection("users")
```

##### Create
verb: insert

```
> db.users.insert(
	{
		username: "millie11", 
		active:true, 
		created: new Date(), 
		name: {first: "millie", last: "walsh"}
	}
);
```

```
>  db.users.insert({username: "john7", active:true, created: new Date(), name: {first: "John"}});
```
Note: not all parts of the document are required. No problem. Flexibility. 

Q: Could this be problematic?

##### Read
verb: find

```
> db.users.findOne();
```

```
> db.users.find();
```

```
> db.talent.find().pretty()
```

Find by field value:

```
> db.users.find({username: "millie11"});
```

Subdocument: 

```
> db.users.find({"name.first":"millie"});
```

```
> db.users.find({name:{first:"millie", last:"walsh"}});
```

##### Update
verb: update

Full object:

```
> db.users.update({username: "john7"}, {username: "john7", active:true, created: new Date(), name: {first: "John", last: "Lundberg"}});
```


$set and $currentDate

```
db.users.updateOne(
	{"name.first":"millie"}, 
		{
			$set: {"favorites.food": "tomato"}, 
			$currentDate: {lastModified: true}
		}
);
```

Upsert: If it doesn't exist create it.


##### Delete
verb: remove/deleteMany/deleteOne

```
db.users.deleteMany({});
db.users.remove({});
db.users.deleteOne({});
```

```
> db.users.remove({username: "milliUser"});
```

```
> db.users.remove({"_id": ObjectId("57e2a9d87938dae4dcea00af")});
```

#### More Finds
Update user to show more ways BSON can be structured.
Other: $gt, $lt, $in, $elemMatch, $exists:

```
> db.users.update({username:"millie11"}, {username: "millie11", active:true, created: new Date(), name: {first: "millie", last: "walsh"}, numberPets: 0, scores: [34, 67, 89], favorites: {food: "tomato", artist: "Picasso" },  family:[{rel: "father", name:"Richard", age: 60}, {rel: "sister", name: "Amy", age: 25}]});
```

#####$and $or

```
> db.users.find( { $and: [{"name.first": "millie"}, {"name.last": "walsh"} ] } );
```

```
> db.users.find({$or: [ {age: 27}, {username: "john7"} ] });
```

#####$in

```
> db.users.find( { scores: { $in: [34, 67] } } );
```

#####$gt and $lt

```
> db.users.find({age: {$gt:20}});
```

```
> db.users.find({age: {$lt:60}});
```
#####$exists
```
> db.users.find({family :{$exists: true}});
```

##### Drop Database

DANGER - Must be in the db you want to drop. Use <dbname>

```
db.dropDatabase();
```

-----
##### Assignment
In mongo shell (more sporadic):
```
pwd()

load("./prime/nu/lecture/mongo/prime_mongo_cli_00/bios.js")
```

In terminal
```
mongoimport --db challenge --collection bios --drop --file bios.json
```

-----


6/20/16 - Rewritten and organized for Nu
9/21/16 - Modified for Pi
	
Heavily influenced by: https://docs.google.com/document/d/1yLDiF7zYvD7qj4CYnSpiEHnvxLKjuejvvWh4qW6cgQY/edit#heading=h.dbi5rzfy9l76 
