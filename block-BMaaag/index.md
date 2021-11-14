writeCode

Write code to:-

- create a database named `mountains`
- a collection inside that database named `himalayas`
- insert 1 document into that collection `{name: 'Dhauldhar range', height: '4000 mtrs'}`

- insert multiple document using insertMany command
- find all documents from mountains
- find a single document using name

use moutains
switched to db moutains
> show collection
uncaught exception: Error: don't know how to show [collection] :
shellHelper.show@src/mongo/shell/utils.js:1211:11
shellHelper@src/mongo/shell/utils.js:838:15
@(shellhelp2):1:1
> show collections
himalayas
> db.himalayas.find()
{ "_id" : ObjectId("61908b876585021a6f8c8819"), "name" : "Dhauldhar range", "height" : "4000 mtrs" }
>db.himalayas.insertMany([{name:"Mount Everest",height:"8849m"},{name:"Kanchunjunga",height:"8500m"}])
{
	"acknowledged" : true,
	"insertedIds" : [
		ObjectId("61908e99baf2666f4ac9091e"),
		ObjectId("61908e99baf2666f4ac9091f")
	]
}
> db.himalayas.find()
{ "_id" : ObjectId("61908b876585021a6f8c8819"), "name" : "Dhauldhar range", "height" : "4000 mtrs" }
{ "_id" : ObjectId("61908e99baf2666f4ac9091e"), "name" : "Mount Everest", "height" : "8849m" }
{ "_id" : ObjectId("61908e99baf2666f4ac9091f"), "name" : "Kanchunjunga", "height" : "8500m" }
db.himalayas.findOne({name:"Mount Everest"})
{
	"_id" : ObjectId("61908e99baf2666f4ac9091e"),
	"name" : "Mount Everest",
	"height" : "8849m"
}
