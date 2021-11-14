writeCode

Write code to execute below expressions.

1. Create a database named `blog`.
2. Create a collection called 'articles'.
3. Insert multiple documents(at least 3) into articles. It should have fields

- title as string
- createdAt as date
- details as String
- author as nested object
  - author should have
    - name
    - email
    - age
    - example author: {name: 'abc', email: 'abc@gmail', age: 25}
- tags : Array of strings like ['html', 'css']

```js
// An article should look like in the database
{
  _id: 'some_random_id',
  title: '',
  details: '',
  author: {
    name: '',
    email: '',
    age: ''
  },
  tags: ['js', 'mongo']
}
```

4. Find all the articles using `db.COLLECTION_NAME.find()`
5. Find a document using \_id field.
6. 1. Find documents using title
7. 2. Find documents using author's name field.
8. Find document using a specific tag.

9. Update title of a document using its \_id field.
10. Update a author's name using article's title.
11. rename details field to description from all articles in articles collection.
12. Add additional tag in a specific document.

13. Update an article's title using $set and without $set.

- Write the differences here ?

13. find an article using title and increment it's auhtor's age by 5.

14. Delete a document using \_id field with `db.COLLECTION_NAME.remove()`.

// Sample data

```js
db.users.insertMany([
  {
    age: 49,
    name: "Maurice Brock",
    email: "wuk@hibpiz.ch",
    gender: "Female",
    sports: ["cricket", "football"],
    scores: [24, 35, 18, 16],
    weight: 45,
  },
  {
    age: 37,
    birthday: "7/15/1986",
    name: "Virgie Cunningham",
    email: "ezogafa@de.gm",
    gender: "Male",
    sports: ["football"],
    scores: [17, 35, 43],
    weight: 52,
  },
  {
    age: 48,
    birthday: "5/14/1961",
    name: "Alexander Holt",
    email: "han@mu.pe",
    gender: "Male",
    sports: ["cricket", "football", "TT"],
    scores: [24, 30, 16],
    weight: 55,
  },
  {
    age: 53,
    birthday: "11/15/1963",
    name: "Derek Dawson",
    email: "polril@now.de",
    gender: "Male",
    sports: ["cricket", "hockey"],
    scores: [20, 15, 38, 23],
    weight: 49,
  },
  {
    age: 34,
    birthday: "7/24/1964",
    name: "Cynthia Cobb",
    email: "wujjarpob@jecimpar.gu",
    gender: "Female",
    sports: ["cricket"],
    scores: [41, 17, 28],
    weight: 51,
  },
  {
    age: 33,
    birthday: "10/26/1982",
    name: "Isabella Atkins",
    email: "ononuzas@givhoz.ca",
    gender: "Female",
    sports: ["cricket", "football", "hockey", "TT"],
    scores: [14, 38, 29, 45, 20],
    weight: 49,
  },
  {
    age: 47,
    birthday: "10/12/1978",
    name: "Katharine Bryan",
    email: "zo@pebi.sa",
    gender: "Male",
    sports: ["TT", "hockey", "khokho"],
    scores: [27, 20, 34],
    weight: 58,
  },
  {
    age: 41,
    birthday: "1/28/1991",
    name: "Beatrice Fleming",
    email: "ufufsa@pujizren.tk",
    gender: "Female",
    sports: ["football", "khokho"],
    scores: [30, 20, 15, 29, 43],
    weight: 47,
  },
  {
    age: 26,
    birthday: "3/23/1998",
    name: "Tom Fields",
    email: "wasodjow@ofaba.gf",
    gender: "Female",
    sports: ["khokho"],
    scores: [37, 29, 18, 43, 49],
    weight: 50,
  },
  {
    age: 33,
    birthday: "11/14/1960",
    name: "Steve Ortega",
    email: "dupus@ca.ls",
    gender: "Female",
    sports: ["cricket", "football", "hockey"],
    scores: [12, 15, 20],
    weight: 51,
  },
  {
    age: 24,
    birthday: "1/5/1994",
    name: "Suraj Kumar",
    weight: 50,
    gender: "Male",
    sports: ["football", "cricket", "TT"],
  },
]);
```

Insert above data into database to perform below queries:-

- Find all males who play cricket.
- Update user with extra golf field in sports array whose name is "Steve Ortega".
- Find all users who play either 'football' or 'cricket'.
- Find all users whose name includes 'ri' in their name.


use blog
switched to db blog
> db.createCollection("articles")
{ "ok" : 1 }
> show collections
articles
> db.articles.insert([{)
...     "title":"test1",
...     "createdAt":111,
...     "details":"test",
...     "author":{
...         "name":"himanshu",
...         "email":"test1@gmail.com",
...         "age":27
...     },
...     "tags":["html","css"]
... },{
...     "title":"test2",
...     "createdAt":222,
...     "details":"test",
...     "author":{
...         "name":"himanshu",
...         "email":"test2@gmail.com",
...         "age":27
...     },
...     "tags":["html","css"]
... },{
...     "title":"test3",
...     "createdAt":333,
...     "details":"test",
...     "author":{
...         "name":"rohit",
...         "email":"test3@gmail.com",
...         "age":27
...     },
...     "tags":["html","css"]
... },{
...     "title":"test4",
...     "createdAt":444,
...     "details":"test",
...     "author":{
...         "name":"himanshu",
...         "email":"test4@gmail.com",
...         "age":27
...     },
...     "tags":["html","css"]
... }])
uncaught exception: SyntaxError: expected property name, got ')' :
@(shell):1:21
> db.articles.insert([{     "title":"test1",     "createdAt":111,     "details":"test",     "author":{         "name":"himanshu",         "email":"test1@gmail.com",         "age":27     },     "tags":["html","css"] },{     "title":"test2",     "createdAt":222,     "details":"test",     "author":{         "name":"himanshu",         "email":"test2@gmail.com",         "age":27     },     "tags":["html","css"] },{     "title":"test3",     "createdAt":333,     "details":"test",     "author":{         "name":"rohit",         "email":"test3@gmail.com",         "age":27     },     "tags":["html","css"] },{     "title":"test4",     "createdAt":444,     "details":"test",     "author":{         "name":"himanshu",         "email":"test4@gmail.com",         "age":27     },     "tags":["html","css"] }])

BulkWriteResult({
	"writeErrors" : [ ],
	"writeConcernErrors" : [ ],
	"nInserted" : 4,
	"nUpserted" : 0,
	"nMatched" : 0,
	"nModified" : 0,
	"nRemoved" : 0,
	"upserted" : [ ]
})
> db.articles.find().pretty()
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90920"),
	"title" : "test1",
	"createdAt" : 111,
	"details" : "test",
	"author" : {
		"name" : "himanshu",
		"email" : "test1@gmail.com",
		"age" : 27
	},
	"tags" : [
		"html",
		"css"
	]
}
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90921"),
	"title" : "test2",
	"createdAt" : 222,
	"details" : "test",
	"author" : {
		"name" : "himanshu",
		"email" : "test2@gmail.com",
		"age" : 27
	},
	"tags" : [
		"html",
		"css"
	]
}
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90922"),
	"title" : "test3",
	"createdAt" : 333,
	"details" : "test",
	"author" : {
		"name" : "rohit",
		"email" : "test3@gmail.com",
		"age" : 27
	},
	"tags" : [
		"html",
		"css"
	]
}
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90923"),
	"title" : "test4",
	"createdAt" : 444,
	"details" : "test",
	"author" : {
		"name" : "himanshu",
		"email" : "test4@gmail.com",
		"age" : 27
	},
	"tags" : [
		"html",
		"css"
	]
}


6)
>db.articles.find({title:"test3"}).pretty()
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90922"),
	"title" : "test3",
	"createdAt" : 333,
	"details" : "test",
	"author" : {
		"name" : "rohit",
		"email" : "test3@gmail.com",
		"age" : 27
	},
	"tags" : [
		"html",
		"css"
	]
}
7)
>d/.,  bnmb.articles.find({"author.name":"cat"}).pretty()
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90921"),
	"title" : "tiger",
	"createdAt" : 222,
	"author" : {
		"name" : "cat"
	},
	"tags" : [
		"html",
		"css",
		"java"
	],
	"description" : "test"
}
8)
>db.articles.find({tags:"html"}).pretty()
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90920"),
	"title" : "test1",
	"createdAt" : 111,
	"details" : "test",
	"author" : {
		"name" : "himanshu",
		"email" : "test1@gmail.com",
		"age" : 27
	},
	"tags" : [
		"html",
		"css"
	]
}
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90921"),
	"title" : "test2",
	"createdAt" : 222,
	"details" : "test",
	"author" : {
		"name" : "himanshu",
		"email" : "test2@gmail.com",
		"age" : 27
	},
	"tags" : [
		"html",
		"css"
	]
}
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90922"),
	"title" : "test3",
	"createdAt" : 333,
	"details" : "test",
	"author" : {
		"name" : "rohit",
		"email" : "test3@gmail.com",
		"age" : 27
	},
	"tags" : [
		"html",
		"css"
	]
}
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90923"),
	"title" : "test4",
	"createdAt" : 444,
	"details" : "test",
	"author" : {
		"name" : "himanshu",
		"email" : "test4@gmail.com",
		"age" : 27
	},
	"tags" : [
		"html",
		"css"
	]
} 

9)
>db.articles.update({_id:ObjectId("6190dfebbaf2666f4ac90923")},{$set:{title:"aditya"}})
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })

10)
>db.articles.update({title:"test2"},{$set:{author:{name:"cat"}}})
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
> db.articles.find().pretty()
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90920"),
	"title" : "test1",
	"createdAt" : 111,
	"details" : "test",
	"author" : {
		"name" : "himanshu",
		"email" : "test1@gmail.com",
		"age" : 27
	},
	"tags" : [
		"html",
		"css"
	]
}
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90921"),
	"title" : "test2",
	"createdAt" : 222,
	"details" : "test",
	"author" : {
		"name" : "cat"
	},
	"tags" : [
		"html",
		"css"
	]
}
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90922"),
	"author" : {
		"$set" : {
			"name" : "cheetah"
		}
	}
}
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90923"),
	"title" : "aditya",
	"createdAt" : 444,
	"details" : "test",
	"author" : {
		"name" : "himanshu",
		"email" : "test4@gmail.com",
		"age" : 27
	},
	"tags" : [
		"html",
		"css"
	]
}

11)
>db.articles.updateMany({},{$rename:{"details":"description"}})
{ "acknowledged" : true, "matchedCount" : 4, "modifiedCount" : 3 }
> db.articles.find().pretty()
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90920"),
	"title" : "test1",
	"createdAt" : 111,
	"author" : {
		"name" : "himanshu",
		"email" : "test1@gmail.com",
		"age" : 27
	},
	"tags" : [
		"html",
		"css"
	],
	"description" : "test"
}
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90921"),
	"title" : "test2",
	"createdAt" : 222,
	"author" : {
		"name" : "cat"
	},
	"tags" : [
		"html",
		"css"
	],
	"description" : "test"
}
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90922"),
	"author" : {
		"$set" : {
			"name" : "cheetah"
		}
	}
}
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90923"),
	"title" : "aditya",
	"createdAt" : 444,
	"author" : {
		"name" : "himanshu",
		"email" : "test4@gmail.com",
		"age" : 27
	},
	"tags" : [
		"html",
		"css"
	],
	"description" : "test"
}

12)
>db.articles.update({title:"test2"},{$push:{tags:"java"}})
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
> db.articles.find().pretty()
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90920"),
	"title" : "test1",
	"createdAt" : 111,
	"author" : {
		"name" : "himanshu",
		"email" : "test1@gmail.com",
		"age" : 27
	},
	"tags" : [
		"html",
		"css"
	],
	"description" : "test"
}
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90921"),
	"title" : "test2",
	"createdAt" : 222,
	"author" : {
		"name" : "cat"
	},
	"tags" : [
		"html",
		"css",
		"java"
	],
	"description" : "test"
}
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90922"),
	"author" : {
		"$set" : {
			"name" : "cheetah"
		}
	}
}
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90923"),
	"title" : "aditya",
	"createdAt" : 444,
	"author" : {
		"name" : "himanshu",
		"email" : "test4@gmail.com",
		"age" : 27
	},
	"tags" : [
		"html",
		"css"
	],
	"description" : "test"
}

13) with set
>db.articles.update({title:"test2"},{$set:{title:"tiger"}})
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
> db.articles.find().pretty()
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90920"),
	"title" : "test1",
	"createdAt" : 111,
	"author" : {
		"name" : "himanshu",
		"email" : "test1@gmail.com",
		"age" : 27
	},
	"tags" : [
		"html",
		"css"
	],
	"description" : "test"
}
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90921"),
	"title" : "tiger",
	"createdAt" : 222,
	"author" : {
		"name" : "cat"
	},
	"tags" : [
		"html",
		"css",
		"java"
	],
	"description" : "test"
}
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90922"),
	"author" : {
		"$set" : {
			"name" : "cheetah"
		}
	}
}
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90923"),
	"title" : "aditya",
	"createdAt" : 444,
	"author" : {
		"name" : "himanshu",
		"email" : "test4@gmail.com",
		"age" : 27
	},
	"tags" : [
		"html",
		"css"
	],
	"description" : "test"
}

 without set

>db.articles.update({title:"test1"},{title:"mouse"})
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
> db.articles.find().pretty()
{ "_id" : ObjectId("6190dfebbaf2666f4ac90920"), "title" : "mouse" }
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90921"),
	"title" : "tiger",
	"createdAt" : 222,
	"author" : {
		"name" : "cat"
	},
	"tags" : [
		"html",
		"css",
		"java"
	],
	"description" : "test"
}
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90922"),
	"author" : {
		"$set" : {
			"name" : "cheetah"
		}
	}
}
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90923"),
	"title" : "aditya",
	"createdAt" : 444,
	"author" : {
		"name" : "himanshu",
		"email" : "test4@gmail.com",
		"age" : 27
	},
	"tags" : [
		"html",
		"css"
	],
	"description" : "test"
}

14)
>db.articles.update({title:"aditya"},{$inc:{"author.age":2}})
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
> db.articles.find().pretty()
{ "_id" : ObjectId("6190dfebbaf2666f4ac90920"), "title" : "mouse" }
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90921"),
	"title" : "tiger",
	"createdAt" : 222,
	"author" : {
		"name" : "cat"
	},
	"tags" : [
		"html",
		"css",
		"java"
	],
	"description" : "test"
}
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90922"),
	"author" : {
		"$set" : {
			"name" : "cheetah"
		}
	}
}
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90923"),
	"title" : "aditya",
	"createdAt" : 444,
	"author" : {
		"name" : "himanshu",
		"email" : "test4@gmail.com",
		"age" : 29
	},
	"tags" : [
		"html",
		"css"
	],
	"description" : "test"
}

15)
>db.articles.remove({"_id" : ObjectId("6190dfebbaf2666f4ac90920")})
WriteResult({ "nRemoved" : 1 })
> db.articles.find().pretty()
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90921"),
	"title" : "tiger",
	"createdAt" : 222,
	"author" : {
		"name" : "cat"
	},
	"tags" : [
		"html",
		"css",
		"java"
	],
	"description" : "test"
}
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90922"),
	"author" : {
		"$set" : {
			"name" : "cheetah"
		}
	}
}
{
	"_id" : ObjectId("6190dfebbaf2666f4ac90923"),
	"title" : "aditya",
	"createdAt" : 444,
	"author" : {
		"name" : "himanshu",
		"email" : "test4@gmail.com",
		"age" : 29
	},
	"tags" : [
		"html",
		"css"
	],
	"description" : "test"
}

Last Question
1)
>db.users.find({$and:[{gender:"Male"},{sports:"cricket"}]}).pretty()
{
	"_id" : ObjectId("6190f055fc60e7af8b11ea4f"),
	"age" : 48,
	"birthday" : "5/14/1961",
	"name" : "Alexander Holt",
	"email" : "han@mu.pe",
	"gender" : "Male",
	"sports" : [
		"cricket",
		"football",
		"TT"
	],
	"scores" : [
		24,
		30,
		16
	],
	"weight" : 55
}
{
	"_id" : ObjectId("6190f055fc60e7af8b11ea50"),
	"age" : 53,
	"birthday" : "11/15/1963",
	"name" : "Derek Dawson",
	"email" : "polril@now.de",
	"gender" : "Male",
	"sports" : [
		"cricket",
		"hockey"
	],
	"scores" : [
		20,
		15,
		38,
		23
	],
	"weight" : 49
}
{
	"_id" : ObjectId("6190f055fc60e7af8b11ea57"),
	"age" : 24,
	"birthday" : "1/5/1994",
	"name" : "Suraj Kumar",
	"weight" : 50,
	"gender" : "Male",
	"sports" : [
		"football",
		"cricket",
		"TT"
	]
}

2)
db.users.update({name:"Steve Ortega"},{$push:{sports:"golf"}})
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
> db.users.find().pretty()
{
	"_id" : ObjectId("6190f055fc60e7af8b11ea4d"),
	"age" : 49,
	"name" : "Maurice Brock",
	"email" : "wuk@hibpiz.ch",
	"gender" : "Female",
	"sports" : [
		"cricket",
		"football"
	],
	"scores" : [
		24,
		35,
		18,
		16
	],
	"weight" : 45
}
{
	"_id" : ObjectId("6190f055fc60e7af8b11ea4e"),
	"age" : 37,
	"birthday" : "7/15/1986",
	"name" : "Virgie Cunningham",
	"email" : "ezogafa@de.gm",
	"gender" : "Male",
	"sports" : [
		"football"
	],
	"scores" : [
		17,
		35,
		43
	],
	"weight" : 52
}
{
	"_id" : ObjectId("6190f055fc60e7af8b11ea4f"),
	"age" : 48,
	"birthday" : "5/14/1961",
	"name" : "Alexander Holt",
	"email" : "han@mu.pe",
	"gender" : "Male",
	"sports" : [
		"cricket",
		"football",
		"TT"
	],
	"scores" : [
		24,
		30,
		16
	],
	"weight" : 55
}
{
	"_id" : ObjectId("6190f055fc60e7af8b11ea50"),
	"age" : 53,
	"birthday" : "11/15/1963",
	"name" : "Derek Dawson",
	"email" : "polril@now.de",
	"gender" : "Male",
	"sports" : [
		"cricket",
		"hockey"
	],
	"scores" : [
		20,
		15,
		38,
		23
	],
	"weight" : 49
}
{
	"_id" : ObjectId("6190f055fc60e7af8b11ea51"),
	"age" : 34,
	"birthday" : "7/24/1964",
	"name" : "Cynthia Cobb",
	"email" : "wujjarpob@jecimpar.gu",
	"gender" : "Female",
	"sports" : [
		"cricket"
	],
	"scores" : [
		41,
		17,
		28
	],
	"weight" : 51
}
{
	"_id" : ObjectId("6190f055fc60e7af8b11ea52"),
	"age" : 33,
	"birthday" : "10/26/1982",
	"name" : "Isabella Atkins",
	"email" : "ononuzas@givhoz.ca",
	"gender" : "Female",
	"sports" : [
		"cricket",
		"football",
		"hockey",
		"TT"
	],
	"scores" : [
		14,
		38,
		29,
		45,
		20
	],
	"weight" : 49
}
{
	"_id" : ObjectId("6190f055fc60e7af8b11ea53"),
	"age" : 47,
	"birthday" : "10/12/1978",
	"name" : "Katharine Bryan",
	"email" : "zo@pebi.sa",
	"gender" : "Male",
	"sports" : [
		"TT",
		"hockey",
		"khokho"
	],
	"scores" : [
		27,
		20,
		34
	],
	"weight" : 58
}
{
	"_id" : ObjectId("6190f055fc60e7af8b11ea54"),
	"age" : 41,
	"birthday" : "1/28/1991",
	"name" : "Beatrice Fleming",
	"email" : "ufufsa@pujizren.tk",
	"gender" : "Female",
	"sports" : [
		"football",
		"khokho"
	],
	"scores" : [
		30,
		20,
		15,
		29,
		43
	],
	"weight" : 47
}
{
	"_id" : ObjectId("6190f055fc60e7af8b11ea55"),
	"age" : 26,
	"birthday" : "3/23/1998",
	"name" : "Tom Fields",
	"email" : "wasodjow@ofaba.gf",
	"gender" : "Female",
	"sports" : [
		"khokho"
	],
	"scores" : [
		37,
		29,
		18,
		43,
		49
	],
	"weight" : 50
}
{
	"_id" : ObjectId("6190f055fc60e7af8b11ea56"),
	"age" : 33,
	"birthday" : "11/14/1960",
	"name" : "Steve Ortega",
	"email" : "dupus@ca.ls",
	"gender" : "Female",
	"sports" : [
		"cricket",
		"football",
		"hockey",
		"golf"
	],
	"scores" : [
		12,
		15,
		20
	],
	"weight" : 51
}
{
	"_id" : ObjectId("6190f055fc60e7af8b11ea57"),
	"age" : 24,
	"birthday" : "1/5/1994",
	"name" : "Suraj Kumar",
	"weight" : 50,
	"gender" : "Male",
	"sports" : [
		"football",
		"cricket",
		"TT"
	]
}

3)
db.users.find({sports:{$in:["football","cricket"]}}).pretty()
{
	"_id" : ObjectId("6190f055fc60e7af8b11ea4d"),
	"age" : 49,
	"name" : "Maurice Brock",
	"email" : "wuk@hibpiz.ch",
	"gender" : "Female",
	"sports" : [
		"cricket",
		"football"
	],
	"scores" : [
		24,
		35,
		18,
		16
	],
	"weight" : 45
}
{
	"_id" : ObjectId("6190f055fc60e7af8b11ea4e"),
	"age" : 37,
	"birthday" : "7/15/1986",
	"name" : "Virgie Cunningham",
	"email" : "ezogafa@de.gm",
	"gender" : "Male",
	"sports" : [
		"football"
	],
	"scores" : [
		17,
		35,
		43
	],
	"weight" : 52
}
{
	"_id" : ObjectId("6190f055fc60e7af8b11ea4f"),
	"age" : 48,
	"birthday" : "5/14/1961",
	"name" : "Alexander Holt",
	"email" : "han@mu.pe",
	"gender" : "Male",
	"sports" : [
		"cricket",
		"football",
		"TT"
	],
	"scores" : [
		24,
		30,
		16
	],
	"weight" : 55
}
{
	"_id" : ObjectId("6190f055fc60e7af8b11ea50"),
	"age" : 53,
	"birthday" : "11/15/1963",
	"name" : "Derek Dawson",
	"email" : "polril@now.de",
	"gender" : "Male",
	"sports" : [
		"cricket",
		"hockey"
	],
	"scores" : [
		20,
		15,
		38,
		23
	],
	"weight" : 49
}
{
	"_id" : ObjectId("6190f055fc60e7af8b11ea51"),
	"age" : 34,
	"birthday" : "7/24/1964",
	"name" : "Cynthia Cobb",
	"email" : "wujjarpob@jecimpar.gu",
	"gender" : "Female",
	"sports" : [
		"cricket"
	],
	"scores" : [
		41,
		17,
		28
	],
	"weight" : 51
}
{
	"_id" : ObjectId("6190f055fc60e7af8b11ea52"),
	"age" : 33,
	"birthday" : "10/26/1982",
	"name" : "Isabella Atkins",
	"email" : "ononuzas@givhoz.ca",
	"gender" : "Female",
	"sports" : [
		"cricket",
		"football",
		"hockey",
		"TT"
	],
	"scores" : [
		14,
		38,
		29,
		45,
		20
	],
	"weight" : 49
}
{
	"_id" : ObjectId("6190f055fc60e7af8b11ea54"),
	"age" : 41,
	"birthday" : "1/28/1991",
	"name" : "Beatrice Fleming",
	"email" : "ufufsa@pujizren.tk",
	"gender" : "Female",
	"sports" : [
		"football",
		"khokho"
	],
	"scores" : [
		30,
		20,
		15,
		29,
		43
	],
	"weight" : 47
}
{
	"_id" : ObjectId("6190f055fc60e7af8b11ea56"),
	"age" : 33,
	"birthday" : "11/14/1960",
	"name" : "Steve Ortega",
	"email" : "dupus@ca.ls",
	"gender" : "Female",
	"sports" : [
		"cricket",
		"football",
		"hockey",
		"golf"
	],
	"scores" : [
		12,
		15,
		20
	],
	"weight" : 51
}
{
	"_id" : ObjectId("6190f055fc60e7af8b11ea57"),
	"age" : 24,
	"birthday" : "1/5/1994",
	"name" : "Suraj Kumar",
	"weight" : 50,
	"gender" : "Male",
	"sports" : [
		"football",
		"cricket",
		"TT"
	]
}

4)
db.users.find({"name" : {$regex : "ri"}}).pretty()
{
	"_id" : ObjectId("6190f055fc60e7af8b11ea4d"),
	"age" : 49,
	"name" : "Maurice Brock",
	"email" : "wuk@hibpiz.ch",
	"gender" : "Female",
	"sports" : [
		"cricket",
		"football"
	],
	"scores" : [
		24,
		35,
		18,
		16
	],
	"weight" : 45
}
{
	"_id" : ObjectId("6190f055fc60e7af8b11ea53"),
	"age" : 47,
	"birthday" : "10/12/1978",
	"name" : "Katharine Bryan",
	"email" : "zo@pebi.sa",
	"gender" : "Male",
	"sports" : [
		"TT",
		"hockey",
		"khokho"
	],
	"scores" : [
		27,
		20,
		34
	],
	"weight" : 58
}
{
	"_id" : ObjectId("6190f055fc60e7af8b11ea54"),
	"age" : 41,
	"birthday" : "1/28/1991",
	"name" : "Beatrice Fleming",
	"email" : "ufufsa@pujizren.tk",
	"gender" : "Female",
	"sports" : [
		"football",
		"khokho"
	],
	"scores" : [
		30,
		20,
		15,
		29,
		43
	],
	"weight" : 47
}