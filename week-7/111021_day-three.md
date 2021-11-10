# Mongoose
When writing to a database, it is often important to ensure the data is as expected. Enter schema-validation with Mongoose.

Mongoose is an object data modeling (ODM) library. "A straight-forward, schema-based solution to model your application data"

## Getting Started
Mongoose replaces the mongodb driver
Runs mongodb queries under the hood
Make a new directory named mongoose-example
```
cd mongoose-example
npm init -y
npm install mongoose
```


## Concept: Schemas
A database schema outlines the expected structure of the data that will be inserted into a collection

A database schema can also define methods on the documents being inserted.
    - defines what that data should look like, and how it should behave.
    - used to create a model
    - definitions are based on SchemaTypes
    

```
const Individual = new mongoose.Schema({
    //these key value pairs are the name of the key and what TYPE you want the value to be
    name: String,
    gender: String,
    age: Number
})

```

## Concept: Model
While the definition of the data's structure is held in the Schema, a Model actually handles the work.
- constructors built using the schema
- enforces definition of schema
- creates a collection based on provided name
- instances of models are documents



## Putting It All Together!

`const Student = mongoose.model("students", Individual);`

Creating an instance of a Model makes a document that can be saved to a collection
That collection is is a lower-case, pluralized version of the Model name
- Model: Student
- Collection: students
- Schema: Individual




