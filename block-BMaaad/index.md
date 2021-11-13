writeCode

Write command to

- List collections from a database.
- create a new collection in your country database which you created recently.

Write code to:-

- crate a database named `weather`
- create a capped collection named `temperature` with maximum of 3 documents and try inserting more than 3 to see the result.
- create a simple collection named `humidity`
- check whether `temperature` collection is capped or not ?
- Delete `humidity` collection and then the entire database(weather).


db.createCollections("pune")
use weather
db.createCollection("temperature")
db.temperature.insert({deg:"22",test:"1",val:"2"})
db.createCollection("humidity")
db.createCollection("test",{capped:true,size:1024,max:3})
db.humidity.isCapped() --> false
db.createCollection("testing",{capped:true,size:3})
db.testing.isCapped() -->true
db.humidity.drop() -->true
db.dropDatabase()