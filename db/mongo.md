## **HONEST WARNING**
**Content in this KB is for me ONLY.**
It contains definitions that explain things in the way that is easiest for me to understand.
_I am not the author of these definitions so check resources section for the origin of definitions._ 


###Collection
It is a group of MongoDB documents.
Collections do not enforce a schema. 

###Database
It is a physical container for collections.

###Document
A document is a set of key-value pairs.  Documents have dynamic schema. Dynamic schema means that documents in the same collection do not need to have the same set of fields or structure, and common fields in a collection's documents may hold different types of data.


## How RDBMS things are called in MongoDB

RDBMS	 	    MongoDB
Database	    Database
Table		    Collection
Tuple/Row	    Document
column		    Field
Table Join	    Embedded Documents
Primary Key	    Primary Key (Default key _id provided by mongodb itself)


## USEFUL COMMANDS

### db.COLLECTION.drop()
	delete collection COLLECTION
Example:
```
> show collections
car
plane
> db.car.drop()
true
> db.car.drop()
false
> show collections
plane
```

### db.createCollection("COLLECTION")
	create collection with name COLLECTION
	for example : db.createCollection("plane")
*   MongoDB creates collection automatically, when you insert some document.
*   normally you will create this collection when you need specify some options for example for capped collection db.createCollection("plane",{"capped":true,"max":5,size:25000}) 

Example:
```
    > db.createCollection("plane",{"capped":true,"max":5,size:25000})
    { "ok" : 1 }
    > db.plane.insert({"name":"Boing 737"})
    WriteResult({ "nInserted" : 1 })
    > db.plane.insert({"name":"Boing 747"})
    WriteResult({ "nInserted" : 1 })
    > db.plane.insert({"name":"Boing 767"})
    WriteResult({ "nInserted" : 1 })
    > db.plane.insert({"name":"Boing 777"})
    WriteResult({ "nInserted" : 1 })
    > db.plane.insert({"name":"Boing 787"})
    WriteResult({ "nInserted" : 1 })
    > db.plane.insert({"name":"Boing 7X7"})
    WriteResult({ "nInserted" : 1 })
    > db.plane.find()
    { "_id" : ObjectId("57f79f9f9505f0047ef35a68"), "name" : "Boing 747" } <- cap was set to 5 so Boing 737 was deleted
    { "_id" : ObjectId("57f79fa29505f0047ef35a69"), "name" : "Boing 767" }
    { "_id" : ObjectId("57f79fa69505f0047ef35a6a"), "name" : "Boing 777" }
    { "_id" : ObjectId("57f79fb49505f0047ef35a6b"), "name" : "Boing 787" }
    { "_id" : ObjectId("57f79fba9505f0047ef35a6c"), "name" : "Boing 7X7" } 
    > db.plane.insert({"name":"Boing 7Y7"})
    WriteResult({ "nInserted" : 1 })
    > db.plane.find()
    { "_id" : ObjectId("57f79fa29505f0047ef35a69"), "name" : "Boing 767" } <= i added 7Y7 so Boing 747 was deleted
    { "_id" : ObjectId("57f79fa69505f0047ef35a6a"), "name" : "Boing 777" }
    { "_id" : ObjectId("57f79fb49505f0047ef35a6b"), "name" : "Boing 787" }
    { "_id" : ObjectId("57f79fba9505f0047ef35a6c"), "name" : "Boing 7X7" }
    { "_id" : ObjectId("57f79fc89505f0047ef35a6d"), "name" : "Boing 7Y7" }
```
### db.dropDatabase() 
	delete current database 

### db.COLLECTION.find().pretty()
    find all documents in collection NAME_OF_COLLECTION and display response as intended json

```
(data setup)
> db.plane.insert({"name":"SS Galaxy" , "speed": 250, "range": 1700})
WriteResult({ "nInserted" : 1 })
> db.plane.insert({"name":"SS Defiant" , "speed": 400, "range": 1220})
WriteResult({ "nInserted" : 1 })
> db.plane.insert({"name":"SS Voyager" , "speed": 205, "range": 2222})
WriteResult({ "nInserted" : 1 })
> db.plane.insert({"name":"SS Consitution" , "speed": 170, "range": 1150})
WriteResult({ "nInserted" : 1 })
> db.plane.insert({"name":"SS Ambassador" , "speed": 220, "range": 2222})
WriteResult({ "nInserted" : 1 })
> db.plane.insert({"name":"SS Akira" , "speed": 500, "range": 3200})
WriteResult({ "nInserted" : 1 })
(end of data setup)
```
#### Find (match exactly) db.plane.find({keyA:valueA, (...) ,keyZ:valueZ}).pretty()
```
> db.plane.find({"speed":500}).pretty()
{
        "_id" : ObjectId("57fe3706ca6a9fc91c6d2b0a"),
        "name" : "SS Akira",
        "speed" : 500,
        "range" : 3200
}
```

#### Find (greater than) > db.plane.find({key : {**$gt**:value}}).pretty()
```
> db.plane.find({"speed" : {**$gt**:205}}).pretty()
{
        "_id" : ObjectId("57fe359aca6a9fc91c6d2b05"),
        "name" : "SS Galaxy",
        "speed" : 250,
        "range" : 1700
}{
        "_id" : ObjectId("57fe35bcca6a9fc91c6d2b06"),
        "name" : "SS Defiant",
        "speed" : 400,
        "range" : 1220
}{
        "_id" : ObjectId("57fe36c4ca6a9fc91c6d2b09"),
        "name" : "SS Ambassador",
        "speed" : 220,
        "range" : 2222
}{
        "_id" : ObjectId("57fe3706ca6a9fc91c6d2b0a"),
        "name" : "SS Akira",
        "speed" : 500,
        "range" : 3200
}
```
#### Find (greater than or equal) > db.plane.find({key : {**$gte**:value}}).pretty()
```
> db.plane.find({"speed" : {**$gte**:205}}).pretty()
{
        "_id" : ObjectId("57fe359aca6a9fc91c6d2b05"),
        "name" : "SS Galaxy",
        "speed" : 250,
        "range" : 1700
}{
        "_id" : ObjectId("57fe35bcca6a9fc91c6d2b06"),
        "name" : "SS Defiant",
        "speed" : 400,
        "range" : 1220
}{
        "_id" : ObjectId("57fe35dbca6a9fc91c6d2b07"),
        "name" : "SS Voyager",
        "speed" : 205,
        "range" : 2222
}{
        "_id" : ObjectId("57fe36c4ca6a9fc91c6d2b09"),
        "name" : "SS Ambassador",
        "speed" : 220,
        "range" : 2222
}{
        "_id" : ObjectId("57fe3706ca6a9fc91c6d2b0a"),
        "name" : "SS Akira",
        "speed" : 500,
        "range" : 3200
}
```

#### Find (less than) > db.plane.find({key : {**$lt**:value}}).pretty()
```
> db.plane.find({"speed" : {$lt:250}}).pretty()
{
        "_id" : ObjectId("57fe35dbca6a9fc91c6d2b07"),
        "name" : "SS Voyager",
        "speed" : 205,
        "range" : 2222
}
{
        "_id" : ObjectId("57fe3698ca6a9fc91c6d2b08"),
        "name" : "SS Consitution",
        "speed" : 170,
        "range" : 1150
}
{
        "_id" : ObjectId("57fe36c4ca6a9fc91c6d2b09"),
        "name" : "SS Ambassador",
        "speed" : 220,
        "range" : 2222
}
```

#### Find (less than or equal) > db.plane.find({key : {**$lte**:value}}).pretty()
```
> db.plane.find({"speed" : {$lte:250}}).pretty()
{
        "_id" : ObjectId("57fe359aca6a9fc91c6d2b05"),
        "name" : "SS Galaxy",
        "speed" : 250,
        "range" : 1700
}{
        "_id" : ObjectId("57fe35dbca6a9fc91c6d2b07"),
        "name" : "SS Voyager",
        "speed" : 205,
        "range" : 2222
}{
        "_id" : ObjectId("57fe3698ca6a9fc91c6d2b08"),
        "name" : "SS Consitution",
        "speed" : 170,
        "range" : 1150
}{
        "_id" : ObjectId("57fe36c4ca6a9fc91c6d2b09"),
        "name" : "SS Ambassador",
        "speed" : 220,
        "range" : 2222
}
```

#### Find (not equals) db.plane.find({key : {$ne:value}}).pretty()
```
> db.plane.find({"speed" : {$ne:170},"speed":{$ne:400}}).pretty()
{
        "_id" : ObjectId("57fe359aca6a9fc91c6d2b05"),
        "name" : "SS Galaxy",
        "speed" : 250,
        "range" : 1700
}
{
        "_id" : ObjectId("57fe35dbca6a9fc91c6d2b07"),
        "name" : "SS Voyager",
        "speed" : 205,
        "range" : 2222
}
{
        "_id" : ObjectId("57fe3698ca6a9fc91c6d2b08"),
        "name" : "SS Consitution",
        "speed" : 170,
        "range" : 1150
}
{
        "_id" : ObjectId("57fe36c4ca6a9fc91c6d2b09"),
        "name" : "SS Ambassador",
        "speed" : 220,
        "range" : 2222
}
{
        "_id" : ObjectId("57fe3706ca6a9fc91c6d2b0a"),
        "name" : "SS Akira",
        "speed" : 500,
        "range" : 3200
}
```

### Find (logical AND and OR)


#### AND
AND in find() is represent by using values that are separated by ','
 
```
> db.plane.find({"range":2222}).pretty()
{
        "_id" : ObjectId("57fe35dbca6a9fc91c6d2b07"),
        "name" : "SS Voyager",
        "speed" : 205,
        "range" : 2222
}{
        "_id" : ObjectId("57fe36c4ca6a9fc91c6d2b09"),
        "name" : "SS Ambassador",
        "speed" : 220,
        "range" : 2222
}
```

#### OR
Or in find() is represent using $or with array$or :[{keyA:ValueA},{keyB:valueB}]
 
```
> db.plane.find({$or:[{"name":"SS Defiant"},{"range":3200}]}).pretty()
{
        "_id" : ObjectId("57fe35bcca6a9fc91c6d2b06"),
        "name" : "SS Defiant",
        "speed" : 400,
        "range" : 1220
}{
        "_id" : ObjectId("57fe3706ca6a9fc91c6d2b0a"),
        "name" : "SS Akira",
        "speed" : 500,
        "range" : 3200
}
```

##### Using OR and AND combo :)

```
> db.plane.find({"speed":{$gt:200},$or:[{"name":"SS Defiant"}]}).pretty()
{
        "_id" : ObjectId("57fe35bcca6a9fc91c6d2b06"),
        "name" : "SS Defiant",
        "speed" : 400,
        "range" : 1220
}
```


#### Projection db.COLLECTION.find({},{keyA:1,keyB:0})
 
Projection works like find but it return selected data rather than all data from document. 
db.COLLECTION.find({},{keyA:1,keyB:0}) where 1 means display, 0 do not display

* by default _id will be always display, so if you don't want display _id simply add ```"_id":0``` for example:
* * ```db.plane.find({},{"_id":0,"name":1})```

```
(use normald find() )
> db.plane.find().pretty()
{
        "_id" : ObjectId("57fe359aca6a9fc91c6d2b05"),
        "name" : "SS Galaxy",
        "speed" : 250,
        "range" : 1700
}
{
        "_id" : ObjectId("57fe35bcca6a9fc91c6d2b06"),
        "name" : "SS Defiant",
        "speed" : 400,
        "range" : 1220
}
{
        "_id" : ObjectId("57fe35dbca6a9fc91c6d2b07"),
        "name" : "SS Voyager",
        "speed" : 205,
        "range" : 2222
}
{
        "_id" : ObjectId("57fe3698ca6a9fc91c6d2b08"),
        "name" : "SS Consitution",
        "speed" : 170,
        "range" : 1150
}
{
        "_id" : ObjectId("57fe36c4ca6a9fc91c6d2b09"),
        "name" : "SS Ambassador",
        "speed" : 220,
        "range" : 2222
}
{
        "_id" : ObjectId("57fe3706ca6a9fc91c6d2b0a"),
        "name" : "SS Akira",
        "speed" : 500,
        "range" : 3200
}
(use projection)

> db.plane.find({},{"name":1})
{ "_id" : ObjectId("57fe359aca6a9fc91c6d2b05"), "name" : "SS Galaxy" }
{ "_id" : ObjectId("57fe35bcca6a9fc91c6d2b06"), "name" : "SS Defiant" }
{ "_id" : ObjectId("57fe35dbca6a9fc91c6d2b07"), "name" : "SS Voyager" }
{ "_id" : ObjectId("57fe3698ca6a9fc91c6d2b08"), "name" : "SS Consitution" }
{ "_id" : ObjectId("57fe36c4ca6a9fc91c6d2b09"), "name" : "SS Ambassador" }
{ "_id" : ObjectId("57fe3706ca6a9fc91c6d2b0a"), "name" : "SS Akira" }
{ "_id" : ObjectId("57ff8191ca6a9fc91c6d2b0b"), "name" : "SS Soverign XXL" }

(to display without _id )
> db.plane.find({},{"_id":0,"name":1}) 

{ "name" : "SS Galaxy" }
{ "name" : "SS Defiant" }
{ "name" : "SS Voyager" }
{ "name" : "SS Consitution" }
{ "name" : "SS Ambassador" }
{ "name" : "SS Akira" }
{ "name" : "SS Soverign XXL" }

```

### Find with limit() (>db.COLLECTION_NAME.find().limit(NUMBER))
limit() method set how many records will be displayed


```
(this is typical find method with projection to display name of the ship only)

> db.plane.find({},{"name":1,"_id":0}).pretty()
{ "name" : "SS Galaxy" }
{ "name" : "SS Defiant" }
{ "name" : "SS Voyager" }
{ "name" : "SS Consitution" }
{ "name" : "SS Ambassador" }
{ "name" : "SS Akira" }
{ "name" : "SS Soverign XXL" }

using limit() method to display first 4 documents
> db.plane.find({},{"name":1,"_id":0}).pretty().limit(4)
{ "name" : "SS Galaxy" }
{ "name" : "SS Defiant" }
{ "name" : "SS Voyager" }
{ "name" : "SS Consitution" }
```


### Sorting with sort() 
db.COLLECTION_NAME.find().sort({KEY:1})
sort method is used to sort records using some criteria.

Specify sorting order:
* 1 is used for ascending order
* -1 is used for descending order.

```
this is list of ships with their speed
> db.plane.find({},{"name":1,"speed":1,"_id":0}).pretty()
{ "name" : "SS Galaxy", "speed" : 250 }
{ "name" : "SS Defiant", "speed" : 400 }
{ "name" : "SS Voyager", "speed" : 205 }
{ "name" : "SS Consitution", "speed" : 170 }
{ "name" : "SS Ambassador", "speed" : 220 }
{ "name" : "SS Akira", "speed" : 500 }
{ "name" : "SS Soverign XXL", "speed" : 466 }

SORT by speed in ascending order:

> db.plane.find({},{"name":1,"speed":1,"_id":0}).pretty().sort({"speed":1})
{ "name" : "SS Consitution", "speed" : 170 }
{ "name" : "SS Voyager", "speed" : 205 }
{ "name" : "SS Ambassador", "speed" : 220 }
{ "name" : "SS Galaxy", "speed" : 250 }
{ "name" : "SS Defiant", "speed" : 400 }
{ "name" : "SS Soverign XXL", "speed" : 466 }
{ "name" : "SS Akira", "speed" : 500 }

SORT by speed in descending order:

> db.plane.find({},{"name":1,"speed":1,"_id":0}).pretty().sort({"speed":-1})
{ "name" : "SS Akira", "speed" : 500 }
{ "name" : "SS Soverign XXL", "speed" : 466 }
{ "name" : "SS Defiant", "speed" : 400 }
{ "name" : "SS Galaxy", "speed" : 250 }
{ "name" : "SS Ambassador", "speed" : 220 }
{ "name" : "SS Voyager", "speed" : 205 }
{ "name" : "SS Consitution", "speed" : 170 }
```
### db.COLLECTION.insert(document) and 
	-- create new document (use save for insert/update)

```
> db.ufo.insert({
    "name":"Borg Cube",
    "description":"A borg generic purpose ship",
    "speed":9.8,cloakable:true
    })
    
WriteResult({ "nInserted" : 1 })

> db.ufo.save({
    "_id" : ObjectId("57fbc1759505f0047ef35a6e"),
    "name":"BORG Cube",
    "description":"A borg generic purpose ship",
    "speed":9.8,cloakable:true
    })
    
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })

> db.ufo.find()

{
    "_id" : ObjectId("57fbc1759505f0047ef35a6e"),
    "name" : "BORG Cube",
    "description" : "A borg generic purpose ship", 
    "speed" : 9.8, 
    "cloakable" : true
    }
```




### db.stats()
    show statistic about database
    
### use DATABASE_NAME
    switch to database DATABASE_NAME

### show dbs
    shows database in this mongo instance
    
* In other to see Your created database on  list you need to insert atleast one document into it.

### show collections
	shows collections :)
	
### update and save document in collection 

#### update db.COLLECTION.update(UPDATE_CRITERIA,NEW_VALUE)
The update() method updates the values in the existing document.

```
(data setup)
> db.plane.insert({"name": "SS Sovereign","speed":475,"range":10000})
WriteResult({ "nInserted" : 1 })

(example)

> db.plane.update({ "speed":475},{$set:{"speed": 450}})
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })

> db.plane.find({"name":"SS Sovereign"}).pretty()
{
        "_id" : ObjectId("57ff8191ca6a9fc91c6d2b0b"),
        "name" : "SS Sovereign",
        "speed" : 450,
        "range" : 10000
}
```

#### save db.COLLECTION.save(document)	
The save() method replaces the existing document with the new document 
```
(data setup)
> db.plane.insert({"name": "SS Sovereign","speed":475,"range":10000})
WriteResult({ "nInserted" : 1 })

(example)

> db.plane.save({ "_id" : ObjectId("57ff8191ca6a9fc91c6d2b0b"),"name" : "SS Soverign XXL", "speed": 466, "range" : 8770})	

(result)

> db.plane.find({"_id": ObjectId("57ff8191ca6a9fc91c6d2b0b")}).pretty()
{
        "_id" : ObjectId("57ff8191ca6a9fc91c6d2b0b"),
        "name" : "SS Soverign XXL",
        "speed" : 466,
        "range" : 8770
}

```

### delete documents and collections
```
> db.animals.insert({"name":"Dog","fly?": false,"underwater?":false})
WriteResult({ "nInserted" : 1 })
> db.animals.insert({"name":"Cat","fly?": false,"underwater?":false})
WriteResult({ "nInserted" : 1 })
> db.animals.insert({"name":"Dragon","fly?": true,"underwater?":false})
WriteResult({ "nInserted" : 1 })
> db.animals.insert({"name":"Hawk","fly?": true,"underwater?":false})
WriteResult({ "nInserted" : 1 })
> db.animals.insert({"name":"Shark","fly?": false,"underwater?":true})
WriteResult({ "nInserted" : 1 })
```

#### remove document by criteria

```
> db.animals.find().pretty()
{
        "_id" : ObjectId("5800e0deca6a9fc91c6d2b0c"),
        "name" : "Dog",
        "fly?" : false,
        "underwater?" : false
}
{
        "_id" : ObjectId("5800e0e5ca6a9fc91c6d2b0d"),
        "name" : "Cat",
        "fly?" : false,
        "underwater?" : false
}
{
        "_id" : ObjectId("5800e0f2ca6a9fc91c6d2b0e"),
        "name" : "Dragon",
        "fly?" : true,
        "underwater?" : false
}
{
        "_id" : ObjectId("5800e0f9ca6a9fc91c6d2b0f"),
        "name" : "Hawk",
        "fly?" : true,
        "underwater?" : false
}
{
        "_id" : ObjectId("5800e10bca6a9fc91c6d2b10"),
        "name" : "Shark",
        "fly?" : false,
        "underwater?" : true
}

> db.animals.remove({"fly?":true})
WriteResult({ "nRemoved" : 2 })

> db.animals.find().pretty()
{
        "_id" : ObjectId("5800e0deca6a9fc91c6d2b0c"),
        "name" : "Dog",
        "fly?" : false,
        "underwater?" : false
}{
        "_id" : ObjectId("5800e0e5ca6a9fc91c6d2b0d"),
        "name" : "Cat",
        "fly?" : false,
        "underwater?" : false
}{
        "_id" : ObjectId("5800e10bca6a9fc91c6d2b10"),
        "name" : "Shark",
        "fly?" : false,
        "underwater?" : true
}
```

#### remove first document
```
> db.animals.remove({"fly?":true},1)
WriteResult({ "nRemoved" : 1 })

> db.animals.find().pretty()
{
        "_id" : ObjectId("5800e364ca6a9fc91c6d2b11"),
        "name" : "Dog",
        "fly?" : false,
        "underwater?" : false
}
{
        "_id" : ObjectId("5800e369ca6a9fc91c6d2b12"),
        "name" : "Cat",
        "fly?" : false,
        "underwater?" : false
}
{
        "_id" : ObjectId("5800e376ca6a9fc91c6d2b14"),
        "name" : "Hawk",
        "fly?" : true,
        "underwater?" : false
}
{
        "_id" : ObjectId("5800e37dca6a9fc91c6d2b15"),
        "name" : "Shark",
        "fly?" : false,
        "underwater?" : true
}
```
#### remove collection

```
> db.animals.remove({})
WriteResult({ "nRemoved" : 5 })

> db.animals.find().pretty()
```

## Indexing

**db.COLLECTION_NAME.createIndex({KEY:1})** (In Mongo 2 was known as ensureIndex and in Mongo 1 was known as .... createIndex . no idea why ;) 

Indexes are special data structures, that store a small portion of the data set in an easy-to-traverse form,so helps with the efficient resolution of queries.
Without indexes, MongoDB must scan every document of a collection to select those documents that match the query statement which is highly inefficient and require MongoDB to process a large volume of data.

Specify sorting order:
* 1 is used for ascending order
* -1 is used for descending order.

What are Indexes in MongoDB?
Indexes support the efficient execution of queries in MongoDB. Without indexes, MongoDB must perform a collection scan, i.e. scan every document in a collection, to select those documents that match the query statement. If an appropriate index exists for a query, MongoDB can use the index to limit the number of documents it must inspect.
by default for a new collection?
By default, MongoDB created the _id collection for every collection.

```
> db.plane.find().pretty()
{
        "_id" : ObjectId("57fe359aca6a9fc91c6d2b05"),
        "name" : "SS Galaxy",
        "speed" : 250,
        "range" : 1700
}
{
        "_id" : ObjectId("57fe35bcca6a9fc91c6d2b06"),
        "name" : "SS Defiant",
        "speed" : 400,
        "range" : 1220
}
{
        "_id" : ObjectId("57fe35dbca6a9fc91c6d2b07"),
        "name" : "SS Voyager",
        "speed" : 205,
        "range" : 2222
}
{
        "_id" : ObjectId("57fe3698ca6a9fc91c6d2b08"),
        "name" : "SS Consitution",
        "speed" : 170,
        "range" : 1150
}
{
        "_id" : ObjectId("57fe36c4ca6a9fc91c6d2b09"),
        "name" : "SS Ambassador",
        "speed" : 220,
        "range" : 2222
}
{
        "_id" : ObjectId("57fe3706ca6a9fc91c6d2b0a"),
        "name" : "SS Akira",
        "speed" : 500,
        "range" : 3200
}
{
        "_id" : ObjectId("57ff8191ca6a9fc91c6d2b0b"),
        "name" : "SS Soverign XXL",
        "speed" : 466,
        "range" : 8770
}

> db.plane.createIndex({"name":1,"speed":-1})
{
        "createdCollectionAutomatically" : false, <- (*1)
        "numIndexesBefore" : 1,
        "numIndexesAfter" : 2,
        "ok" : 1
}

(*1) The createdCollectionAutomatically indicates if the operation created a collection. If a collection does not exist, MongoDB creates the collection as part of the indexing operation.
```

? DON'T WHY this db.animals.remove() does not work 



pretty() display result in formatted way.

```
db.ships.find({KEY:{WHERE:33}})
	-- where WHERE
		$gt - greater than
		$gte - greater than and equals
		$lt - less than
		$lte -  - less than and equals

for example:
	1. Inserting example data:
		db.ships.insert({"number": 25})
		db.ships.insert({"number": 29})
		db.ships.insert({"number": 33})
		db.ships.insert({"number": 37})
		db.ships.insert({"number": 41})		

		db.ships.find() 
			will return all records (keep in mind that _id is random)
			{ "_id" : ObjectId("57f26056938bb376542ca156"), "number" : 25 }
			{ "_id" : ObjectId("57f2605a938bb376542ca157"), "number" : 29 }
			{ "_id" : ObjectId("57f2605e938bb376542ca158"), "number" : 33 }
			{ "_id" : ObjectId("57f26065938bb376542ca159"), "number" : 37 }
			{ "_id" : ObjectId("57f26068938bb376542ca15a"), "number" : 41 }

		db.ships.find({"number":33})
			{ "_id" : ObjectId("57f2605e938bb376542ca158"), "number" : 33 }

		db.ships.find({"number":{$lte:33}})
			{ "_id" : ObjectId("57f26056938bb376542ca156"), "number" : 25 }
			{ "_id" : ObjectId("57f2605a938bb376542ca157"), "number" : 29 }
			{ "_id" : ObjectId("57f2605e938bb376542ca158"), "number" : 33 }

		db.ships.find({"number":{$gte:33}})
			{ "_id" : ObjectId("57f2605e938bb376542ca158"), "number" : 33 }
			{ "_id" : ObjectId("57f26065938bb376542ca159"), "number" : 37 }
			{ "_id" : ObjectId("57f26068938bb376542ca15a"), "number" : 41 }

		db.ships.find({"number":{$gt:33}})
			{ "_id" : ObjectId("57f26065938bb376542ca159"), "number" : 37 }
			{ "_id" : ObjectId("57f26068938bb376542ca15a"), "number" : 41 }

		db.ships.find({"number":{$gte:33}})
			{ "_id" : ObjectId("57f2605e938bb376542ca158"), "number" : 33 }
			{ "_id" : ObjectId("57f26065938bb376542ca159"), "number" : 37 }
			{ "_id" : ObjectId("57f26068938bb376542ca15a"), "number" : 41 }
		
		db.ships.find({"number":{$ne:33}})
			{ "_id" : ObjectId("57f26056938bb376542ca156"), "number" : 25 }
			{ "_id" : ObjectId("57f2605a938bb376542ca157"), "number" : 29 }
			{ "_id" : ObjectId("57f26065938bb376542ca159"), "number" : 37 }
			{ "_id" : ObjectId("57f26068938bb376542ca15a"), "number" : 41 }

	AND in MongoDB ( pass multiple keys by separating them by ','  )
		db.mycol.find({key1:value1, key2:value2}).pretty()
```

###  List all the indexes on a particular collection
db.COLLECTION_NAME.getIndexes()


## explain()
As name suggest it explain how command/method can be used with various information

## Worth to remember:
* In mongodb default database is test. If you didn't create any database then collections will be stored in test database.

* What is the difference between save and insert in Mongo DB?
    * save insert or update a document. Insert does only an insertion. If you don't specify _id in the document while you db.COLLECTION.save(document) then save() method will work same as insert() method

*  covered query  (TODO) is the one in which fields used in the query are part of an index used in the query, and the fields returned in the results are in the same index Since all the fields are covered in the index itself, MongoDB can match the query condition as well as return the result fields using the same index without looking inside the documents.

* Aggregations operations process data records and return computed results. They group values from multiple documents , perform various operations and return result.MongoDB has 3 ways to perform aggregation: the aggregation pipeline, the map-reduce function, and single purpose aggregation methods and commands.

* GridFS is a file system for files that exceed the BSON-document size limit of 16MB. (GridFS divides a file into parts, or chunks, and stores each of those chunks as a separate document.(
* Concurrency MongoDB uses reader-writer locks that allow concurrent readers shared access to a resource, such as a database or collection, but give exclusive access to a single write operation.

* What is Replication in MongoDB? Explain.
  Replication is the process of synchronizing data across multiple servers. Replication provides redundancy and increases data availability. With multiple copies of data on different database servers, replication protects a database from the loss of a single server. Replication also allows you to recover from hardware failure and service interruptions.

* What are Primary and Secondary Replica sets?
  Primary and master nodes are the nodes that can accept writes. MongoDB's replication is 'single-master:' only one node can accept write operations at a time.

  Secondary and slave nodes are read-only nodes that replicate from the primary.

  How does Journaling work in MongoDB?
  When running with journaling, MongoDB stores and applies write operations in memory and in the on-disk journal before the changes are present in the data files on disk. Writes to the journal are atomic, ensuring the consistency of the on-disk journal files. With journaling enabled, MongoDB creates a journal subdirectory within the directory defined by dbPath, which is /data/db by default.