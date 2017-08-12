# Create

## db.collection.insertOne

Insert a single document into a collection.

```javascript
db.movies.insertOne({ "title": "Deadpool", "year": 2016 });
```

## db.collection.insertMany

Insert multiple documents into a collection.

``` javascript
db.movies.insertMany(
  [
    { "_id": 1, "title": "Deadpool", "year": 2016 }, 
    { "_id": 1, "title": "Scarface", "year": 1983 }, // has the same id that Deadpool
    { "_id": 2, "title": "Avatar", "year": 2009 },
  ]
);
```

By default, `insertMany` insert all the documents with the parameter `ordered` set to true,
this means that mongo will insert all the documents one by one from top to bottom but
if in the middle of the operation mongo finds an error with at least one document, the process will stop.

```javascript
db.movies.insertMany(
  [
    { "_id": 1, "title": "Deadpool", "year": 2016 }, 
    { "_id": 1, "title": "Scarface", "year": 1983 }, // has the same id that Deadpool
    { "_id": 2, "title": "Avatar", "year": 2009 },
  ]
);
```

Using the parameter `ordered` with `false` as value, mongo will skip the error (if exist) and
will insert successfuly all the documents that have no errors.


```javascript
db.movies.insertMany(
  [
    { "title": "Deadpool", "year": 2016 }, 
    { "title": "Scarface", "year": 1983 }
  ],
  { "ordered": false }
);
```

## db.collection.insert

```javascript
db.movies.insert({ "title": "Deadpool", "year": 2016 });
```