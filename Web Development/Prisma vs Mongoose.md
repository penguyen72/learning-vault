[Medium Post](https://medium.com/@ibezimchike/comparing-prisma-and-mongoose-fbc42d069c47)
### Summary
This medium post compares the differences between [[Prisma ORM]] and [[Mongoose]]. The main difference between the two is that Prisma is an ORM while Mongoose is an ODM. 

The articles lays out that Prisma is often best when interacting with SQL databases while Mongoose is best interacting with NoSQL databases. This is obvious, however, Prisma can interact with a variety of databases including [[MongoDB]].

Since Prisma is more suited for SQL, the article states that we should just stick with Mongoose to interface with our MongoDB database as it was primarily built for MongoDB. In terms of speed, Mongoose is also faster than Prisma when interacting with a MongoDB database.

### Reasons to use Prisma instead of Mongoose for MongoDB
- Prisma enforces a schema on MongoDB. It presents bloated data types updates as more features are being introduced. Prevents this from happening by enforcing data type definitions in the schema to ensure that data is always in sync.
- Prisma keeps track of database history. Changes are tracked through a migration folder that is added in Prisma directory
- More familiarity with SQL