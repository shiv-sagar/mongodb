1. Create a database named `blog`.

use blog;

2. Create a collection called 'articles'.
db.createCollection("articles");

3. Insert multiple documents(at least 3) into articles. It should have fields

db.articles.insertMany([{title : "one", author: "a", tag: ["express"]},{title : "two", author: "b", tag:["node"]},{title : "three", author: "c",tag : ["nodejs"]}]);

4. Find all the articles using `db.COLLECTION_NAME.find()`

db.articles.find();


5. Find a document using _id field

db.articles.find({"_id" : ObjectId("5eae6cbda22992b159e9ec1d")});

6. Find documents using title and author's name field.

db.articles.find({title: "one", author: "a"});

7. Find document using a specific tag.

db.articles.find({tag :"express"});

8. Update title of a document using its _id field.

db.articles.update({"_id" : ObjectId("5eae6cbda22992b159e9ec1d")},{$set : {title: "ONE"}});

9. Update a author's name using article's title.

db.articles.update({title: "ONE"},{$set : {author : "sagar"});

10. rename details field to description from articles collection. 

db.articles.update({title : "ONE"},{$rename : {details : "description"}});

11. Add additional tag in a specific document.

db.articles.update({title : "ONE"},{$push : {tag : "html"}} );

12. Update an article's tags using $set and without $set.
  - Write the differences here ?



13. Increment an auhtor's age by 5.  

db.articles.update({$inc : {age : 5}});

14. Delete a document using _id field with `db.COLLECTION_NAME.remove()`.

db.articles.remove({title: "ONE"});

Use sample.js data for below queries.

1. Find all males who play cricket.

db.users.find({gender: 'Male', $or: [{sports: 'cricket'}]})


2. Update user with extra golf field in sports array whose name is "Steve Ortega".

db.users.update({name : "Steve Ortega"},{$push : {sports : "golf"}});

3. Find all users who play either 'football' or 'cricket'.

db.users.find({sports : "football" || "cricket"});

4. Find all users whose name includes 'ri' in their name.

db.users.find({name : /\wri/});
