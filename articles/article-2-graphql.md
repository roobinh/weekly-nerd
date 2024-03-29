# What is GraphQL and when should you use it?

## Introduction to databases
Most websites make use of lots of data, which is stored in databases. Databases contain different collections (like users or messages), which each have different columns (like name, timestamp or email address). These collections could also have relations, for example: one user can have multiple messages, and one message can have multiple images.

As you can tell, managing all this data can be quite complex. Once you set up the database, you want to recieve data from the server. Sometimes you want an entire collection, and sometimes you only want very specific data.

## "So... what is GraphQL?"
GraphQL is a query language (QL stands for query language) for your API. Normally when you want to get data from an API, you have a specific URL (endpoint) which you can send get requests to. This URL determines the JSON object that comes back, and sometimes you can manipulate this data for a small amount. This is called an REST API. Rest API's have become more and more common these days.

One big downside of an REST API is that you can't manipulate the data you are recieving from the server, because this is already pre-determined. You just have to accept the data that comes in. This is where GraphQL comes in.

## "How do GraphQL querries work?"

GraphQL make use of query's, in which you define what data you want from the server. For example: 

```
query {
    user(name: "frank") {
        _id
        name
        email
    }
}
```
_The query above returns the id, name and email of all users with name frank_

When you want data from a GraphQL server, you send a POST request with a query. This query defines what data you recieve back. This query contains diffent parts:

<img src="https://cdn-media-1.freecodecamp.org/images/kwrsuL3NrieP9GUyeZe0BNdXNQfQJ-GP4txK" height="300">

- Operation Type
  
  The Query starts with a _Operation Type_, and here you define what you actually want to do. You have two options here: "query" or "mutation". Query returns data from database, mutation changes data in the database.

- Operation Name
  
  Here you define what collection you want data from. For example: users, messages, images

- Variable Definitions
  
  This is optional, and it defines exactly WHAT user/message/image you want to get back. For example: (id: "391238784"), which will only return the user with the corresponding id

- Actual data
  
  Here you define what data you actually want to get back. For example: id, name and email

Thats it! This is what makes GraphQL so easy and convenient to use!

## "But... why would I use GraphQL?"
Good question! If your current REST API doesn't bring any bottleneck to your needs, you could keep using what you are currently using. If you, for example, request a lot of data from your REST API, but only use a small part of it: use GraphQL! Other reasons to start using GraphQL are:

- It's easy to use data from multiple sources
- It uses a easy type system to describe data
- It's very flexible and works with your current code
- It's free!

## Resources
- https://medium.com/devgorilla/what-is-graphql-f0902a959e4
- https://www.freecodecamp.org/news/so-whats-this-graphql-thing-i-keep-hearing-about-baf4d36c20cf/