- sometimes we need to reset the database to its original state. 
- we need to delete all the data and remove all the indexes in it
- to do so, we run the following code

```javascript

// Switch to your database
use yourDatabaseName;

// Get a list of all collections
const collections = db.getCollectionNames();

collections.forEach((collectionName) => {
  const collection = db.getCollection(collectionName);

  // Delete all documents in the collection
  print(`Deleting all documents in collection ${collectionName}`);
  collection.deleteMany({});

  // Drop all indexes except for the _id index
  const indexes = collection.getIndexes();
  indexes.forEach((index) => {
    if (index.name !== "_id_") {
      print(`Dropping index ${index.name} on collection ${collectionName}`);
      collection.dropIndex(index.name);
    }
  });
});

print("All collections have been cleared and non-_id indexes have been dropped.");

```
- run this complete code as is in the mongo shell once we connect to the appsmith database

#### connecting to appsmith database
- connect to mongo shell
```shell
mongo --port 27017
```
- show all the databases available in the cluster
```shell
show databases
```
- select the `appsmith` database
```shell
use appsmith
```