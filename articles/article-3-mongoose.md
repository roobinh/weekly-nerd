# Introduction to Mongoose

## What is Mongoose?
Mongoose is a MongoDB ODM (Object Document Mapping) for nodejs. It provides a simple straight-forward, schema based solution to help you interact with your MongoDB database. MongoDB acts as an intermediate between NodeJS and your MongoDB database.

## What is MongoDB?
So, mongoose acts as an intermediate between your nodejs server and your MongoDB database, but what is MongoDB?

MongoDB is a free, document based, database with a lot of flexability. MongoDB stores data in flexible, JSON-like documents, meaning data fields can vary from document to document and the data structure can be changed over time. This makes MongoDB very pleasant to work with, expecially when prototyping. 

## Mongo terms
So now you know what MongoDB and Mongoose do, let's talk about how to use it.

MongoDB and Mongoose use different terms than your avarage database, so let's clear some words up:
- Collection: A collection in mongoose is equal to a table in SQL, like users. They can hold multiple JSON objects.
- Documents: Documents are equal to records or rows of your collection.
- Schema: Schemas are your document data structure. It defines the properties of the document, like name: String, number: Int or longitude: Float.
- Model: Models are constructors that take a schema, and create an instance of a document based on records in your MongoDB database.

## How does Mongoose work?
Now you know all the terms, let's set up a database and add a user! This requires 5 steps:

**1. Create Database**
Before we start, you need to setup your MongoDB database. You can, for example, do this by using [Mongo Atlas](https://www.mongodb.com/cloud/atlas). 

**2. Install Mongoose**
After creating a MongoDB database, lets install [mongoose](https://www.npmjs.com/package/mongoose) to your nodejs server with the following command:

```
npm install mongoose
```

**3. Connect to your MongoDB Database**
After installing mongoose, we can actually connect to our MongoDB database with the following code:

```javascript
const mongoose = require('mongoose')

var url = //Your db URL/IP here

mongoose.connect(url, { 
    useNewUrlParser: true
}).then(() => {
    console.log('Connected to MongoDB.') //It's that simple!
}).catch(err => {
    console.log(err)
})
```

**4. Creating your Schema(s)**
After connecting to your database, it's time to give some structure to your database. You can do this by creating Schema's:

```javascript
//Schema Example
const mongoose = require('mongoose');
const Schema = mongoose.Schema; 

const userSchema = new Schema({
    name: {
        type: String,
        required: false
    },
    email: {
        type: String,
        required: true
    },
    number: {
        type: Int,
        required: false
    }
});

module.exports = mongoose.model('User', userSchema);
```

**5. Add new document to Schema**
After creating a schema, it's time to add your first document:

```javascript
// create user object
var user = new User({
  name: 'example',
  email: 'example@example.com',
  number: 0646813155
})

// then just save to database with this simple command
user.save()
```

That's it. You just saw how easy it can be to set up a MongoDB database using Mongoose.

## Conclusion
Now that you have your database with documents, you can recieve the document from the server really easy:

```javascript
//mongoose 'find' function
User.find({
  username: 'example'
}).then(retrievedDocument => {
  console.log(retrievedDocument)
})
```

So if you are looking for an easy to use, nodejs compatible, flexible and free database, Mongoose is your way to go. See the links below for more information:
- [https://mongoosejs.com/](https://mongoosejs.com/)
- [https://www.mongodb.com/](https://www.mongodb.com/)
- [https://www.mongodb.com/cloud/atlas](https://www.mongodb.com/cloud/atlas). 

## Resources
https://www.mongodb.com/what-is-mongodb
https://www.quora.com/What-is-Mongoose
https://www.freecodecamp.org/news/introduction-to-mongoose-for-mongodb-d2a7aa593c57/