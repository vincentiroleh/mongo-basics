# MongoDB Fundamentals - (Basic Commands)

Let's talk about [MongoDB](https://www.mongodb.com/) - **The database for modern applications**

MongoDB is a general purpose, document-based, distributed database built for modern application developers and for the cloud era. No database makes you more productive.

## Installation

- [These Link provide instructions to install MongoDB Community Edition for supported Linux systems.](https://docs.mongodb.com/manual/administration/install-on-linux/)

- [These Link provide instructions to install MongoDB Community Edition for macOS systems.](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/)

- [These Link provide instructions to install MongoDB Community Edition for Windows systems.](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-windows/)


## Basic MongoDB commands

- To start the mongoDB shell
```shell
mongo
``` 

- Will create a database named amazon and switch to it
```shell
use amazon
```
- Will show you the current database you're in
```shell
db
```

- Will display all databases you have
```shell
show dbs
```

- Will create a collection called `products` with documents `name` and `macbook` value in the amazon database
```shell
db.products.insert({name: "macbook"})
```

- Will create a collection of users
```shell
db.createCollection("users")
```

- Will show a list of collections in your database
```shell
show collections
```

- Will delete the collection users from the database
```shell
db.users.drop()
```

- Will delete the entire database you are currently on
```shell
db.dropDatabase()
```

- Creates a collection products and inserts one document into it
```shell
db.products.insertOne({name: "macbook", price: 1500, category: "Comp uters"})
```

- Will help us find all the documents in the products collection
```shell
db.products.find()
```

- Will creates many documents into the product collection
```shell
db.products.insertMany([{name: "iPhone 11", price: 1900, category: " Electronics"}, {name: "Headphone", price: 120, category: "Electronics" }])
```

## Reading (flittering) query's from mongoDB

- The `find()` helps us find every document in a collection e.g in products below
```shell
db.products.find()
```

- Returns the `collection` results in JSON format
```shell
db.products.find().pretty()
```

- Finds a specific item passed in, if it exists
```shell
db.products.find({name: "macbook"})

```

- Finds a specific key only
```shell
db.products.find({}, {name: 1})
```

- Finds a specific key only and hide the _id
```shell
db.products.find({}, {name: 1, _id: 0})
```

- Finds a specific key only, hide the _id and show only the first 2
```shell
db.products.find({}, {name: 1, _id:0}).limit(2)
```

- Finds every item that is `less than` 150
```shell
db.products.find({price : {$lt: 150} })
```

- Finds every item that is `less than` or `equal to` 150
```shell
db.products.find({price : {$lte: 150} })
```

- Finds every item that is `grater than` 800
```shell
db.products.find({price : {$gt: 800} })
```

- Finds every item that is `grater than` or `equal to` 800
```shell
db.products.find({price : {$gte: 800} })
```

- Finds every item that its price is `less than` 200 `and` belongs to the category of `Electronics`
```shell
db.products.find({$and: [{price: {$lt:200}}, {category: "Electronics"} ]})
```

- Finds every item that its price is `greater than` 500 `or` belongs to the category of `Electronics`
```shell
db.products.find({$or: [{price: {$gt:500}}, {category: "Electronics"} ]})
```

## Conclusion

Click [HERE](MongoDB_Fundamentals(BasicCommands).pdf) Download PDF version of this tutorial 

**Tomorrow we will talk about updating queries**

__**Tutorials by [Vincent Iroleh](https://iroleh.me/)**__