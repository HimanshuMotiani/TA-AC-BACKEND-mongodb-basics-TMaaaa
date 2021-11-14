writeCode

Write code to:-

- create a database named `sports`.
- list all databases present in local mongod server.
- create 3 collections named `cricket`, `football`, `TT` in sports databse.
- add multiple players in those collections which should have fields like `name`, `age` and `email` and `bid_price`.
- list all collections in sports database.
- rename `TT` collection to `tennis`.
- create a capped collection called `khokho` which should have max 3 documents.
  Try inserting more than 3 and see what happens?
- check whether a collection is capped or not?
- drop all documents from `football` collection.
- delete cricket collection completely.
- delete sports database.
- check which database you are connected to ?
- connect to test database

use sports
show dbs -
admin   0.000GB
config  0.000GB
india   0.000GB
local   0.000GB
test    0.000GB

db.createCollection("cricket")
db.createCollection("football")
db.createCollection("tt")

db.cricket.insertMany([{name:"sachin",age:36,email:"test@gmail.com",bid_price:"100000"},{name:"dhoni",age:36,email:"test@gmail.com",bid_price:"100000"},{name:"dravid",age:36,email:"test@gmail.com",bid_price:"100000"}])

db.football.insertMany([{name:"ronaldo",age:36,email:"test@gmail.com",bid_price:"100000"},{name:"neymar",age:36,email:"test@gmail.com",bid_price:"100000"},{name:"messi",age:36,email:"test@gmail.com",bid_price:"100000"}])

db.tt.insertMany([{name:"test1",age:36,email:"test@gmail.com",bid_price:"100000"},{name:"test2",age:36,email:"test@gmail.com",bid_price:"100000"},{name:"test3",age:36,email:"test@gmail.com",bid_price:"100000"}])

show collections
db.tt.renameCollection("tennis")
db.createCollection("khoko",{capped:true,max:3,size:1024})
db.createCollection("khoko",{capped:true,max:3,size:1024})
db.tennis.isCapped()

db.cricket.drop({})
true
> show collections
khoko
tennis
> db.dropDatabase()
{ "ok" : 1 }
> dbs
uncaught exception: ReferenceError: dbs is not defined :
@(shell):1:1
> show dbs
admin   0.000GB
config  0.000GB
india   0.000GB
local   0.000GB
test    0.000GB
> db
sports
> db.dropDatabase()
{ "ok" : 1 }
> db
sports

use test