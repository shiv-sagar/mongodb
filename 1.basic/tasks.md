#### write commands for following mongodb opertaions

1. create a database named `sports`
// Answer here ..

use sports;

2. list all databases present in local mongod server.
// Answer here..
show dbs;

3. create 3 collections named `cricket`, `football`, `TT` in sports database.
db.createCollection("cricket");
db.createCollection("football");
db.createCollection("TT");

4. add 3 players in each of above collections which should have fields like `name`, `age`, `email`, state and auction_price.

db.cricket.insertMany([{name : "sagar", age : "23", email:"a@gmail.com"}, {name : "sar", age : "24", email:"ac@gmail.com"}, {name : "saar", age : "25", email:"ab@gmail.com"}]);

db.football.insertMany([{name : "sagar", age : "23", email:"a@gmail.com"}, {name : "sar", age : "24", email:"ac@gmail.com"}, {name : "saar", age : "25", email:"ab@gmail.com"}]);

db.TT.insertMany([{name : "sagar", age : "23", email:"a@gmail.com"}, {name : "sar", age : "24", email:"ac@gmail.com"}, {name : "saar", age : "25", email:"ab@gmail.com"}]);


5. list all collections in sports database.
show collections;

6. rename `TT` collection to `tennis`.
db.TT.renameCollection("tennis");


7. create a capped collection called `khokho` which should have max 3 documents.
  Try inserting more than 3 and output the result here ?

db.createCollection("khokho",{capped : true, size : 120000, max : 3});


8. check whether a collection is capped or not?

db.khokho.isCapped();

9. remove all documents from `football` collection.

db.football.remove({});

10. delete cricket collection completely.

db.cricket.drop();


11. rename database sports to games



12. delete sports database. 
db.dropDatabse();