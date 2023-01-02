## **HONEST WARNING**

**Content in this KB is for me ONLY.**
It contains definitions that explain things in the way that is easiest for me to understand.
_I am not the author of these definitions so check resources section for the origin of definitions._

# DynamoDB

DynamoDB is fully manage NoSQL db service that provides fast and predictable perfomance with seamless scalability.

## Basics

* Table (Table in SQL)
    * Item (known as Item in SQL)
    * Column (Attribute)
    * Partition Key and Sort Key (Primary key in SQL, Partition key = Single Primary key while both is known as
      Composite Primary Key).
    * Tables are top-level structure.
    * Performance is managed at the table level.
    * Tunning can happen on a per-table basis.
    * Tables are schema-less.
    * Tables are scoped within a region.Table that in more than one region are not the same as scope of the table.
* DynamoDB Service is a set of tables.

* Data don't need to be predefined except for primary keys.
* Data Types :
    - Scalar - represent 1 value
        * String
        * Number
        * Binary
        * Boolean
        * Null

    - Set represent multiple scalar values
        * Sets can only be of one Scalar type.
        * Empty sets are not supported.
        * Ordering within the set is not preserved.
        * Value must be unique.
    - Document represent complex structure
        * list for storing ordered collection of items
        * map key-value collection where value must be unique
        * you can index only top level

## Dictionary

### Capacity Units

Predefine the throughput at table level, specify:
RCU - read capacity units
WCU - write capacity units

### Partitioning

* It is useful for
    - manageability
    - performance
    - ability
* There are 2 types of partitioning:
  - vertical(split by column)
  - horizontal()
* Dynamo db do not partition until it needs to. It is due to performance and storage reasons.



### putItem
If _Item_ exists , _item_ will be **replaced** otherwise _Item_ will be **created**

### updateItem
if Idem exists then edit an existing itme's attributes or adds a new item to the table if it does not already exists

### deleteItem
Delete a single item using primary key (it will not let you know if item was found or not ..use condition to find out)

all altributes available will be returned * you can use projectionexpression to limit them ,but it will NOT save RCUs,
because dynamodb still read all of them, it is just save network bandwitch

Query is more powverful version of getItem

BatchWriteItem
(up to 16MB of data or up to 25 PUT/DELETE requests ),cannot update items, not atomic, works in parrel , saves time but
not WCU

BatchGetItem

Each operation can retrive up to 16MB of data, or 100 items.
The batch call is not atomic
This batch operation works in parallel
result not ordered

DynamoDB JSON Schema

```json
{
  "AttributeName>": {
    "<DataType>": "<AtttibuteValue>"
  }
}
```


type of quieries

- with known Partition Key (picking right PK is important to save money )
- with unknown Parition Key

consistency models important to understand as it impact cost

- strongly consistent ( return always latest results , uses more RCUs, hihger latency)
- eventually consistent ( reads may not return latest reults, it is use half RCUs of Consistent read,lower latency)
-

Capacity Units

- predefinde throughput for a table

WCU - up to 1kb of data/second Formula Round up (Item size/1KB)
RCU -

- Strongy const
  1RCU - up to 4kb/sec RoundUP(Item size/2KB)
- eventually const
  0.5RCU - up to 4kb/sec roundUp(item size/4KB)/2

roundup to closest 4kb

avoid querying cross partition keys

DynamoDB Streams ...
tracks changes made to DynamoDB table
Changes are tracked on a rolling 24-hour basis
Changes to data are available in an ordered fashion

db streams is code executed when an event occurs
db streams asi a stream of ordered vents which capture all data changes
dynamodb triggers are pieces of code that respond to events in dynamodb streams

DynamoDB strams are useful for build and update caches , run business processes based on table based events
drive real-time analytics
replication and backups
,publishing events to message bus

LSI (Local secondary index)
an index you can create on a table
same partition key, different sort key
max 5lsi per table
lsi can be createdon table creation
WCU and RCU shared
Works in Consistent and eventually consistent modes

GSU (global seconday index)
an index you can create on a table
alternative partition key and sort key
max 5GSI per table
GSI can be created anytie
GSIs have dedicated WCU and RCU
eventually consistent read only
PK and SK dont need to be unique

LSI vs GSI
Same partion/alternative sort key vs alternative pK and SK
max LSI or GSI per table
only created on table vs GSI can be created anytime
LSI share WCU/RCU with base table, GSI have dedicate WCU/RCU
Const and eventually const mode vs eventually const read only
GSI cause additional costs for RCU/WCU and Storage

TTL - time to live
allows us to define when an item will expire
expiry time is stored as an attribute of the item
stored as epoch time
ttl is enabled per table basis
the item will be removed by a background dynamodb process
removeal is best-effort basis (it means it can appear after expire)

PK is limited to 10GB

DAX (DynamoDB Accelerator) is fully managed, in-emory cache.It is desgined as write-through cache
to reduce response from miliseconds to microsecond.
DAX will reduce RCU/WCU on DynamoDBB

DAX consistaency model

data modeling is very important activity to undertake

dynamodb is a key/value store with some document database capabilities. Designe for predicatble access patterns with
single digit milicecond latency and scale to your need (exlcluding burst)
not designed for burst payload

access pattern
is it predictable load?
if yes , scale at fixed schedules
if no, how will you handle throttiling ?
can you isolate unpredictable loads ? overprovision, auto scaling)
Unexpected burst more than 30seconds require better design

item size for 400kb item size limit
expect adhoc queries

do not be afraid to remodel lyour data

migrate data using triggers

your app -> Orginal table(updateItem) -> DynamodDB streams -> lambda - new table
after migration
your app -> new table

hard limit
PK capacity limits:
max WCU = 1000
MAX RCU = 3000
TABLE/ACCOUNT CAPACITY LIMIT EXIST AND IT depends on regions
you can decrease RCU/WCU 4 times a day
PK data limit : 10 GB
table index limits: max 5 of LSI and GSI

item size .max size 400kb

using counters as id have problems
ineffient from a wcu perspective
make every write a multi operation
adds latency

- partition perfromance can limit counters
  ca become a bottlejneck

use UUID as ID

 