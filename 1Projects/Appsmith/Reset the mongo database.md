- sometimes we need to reset the database to its original state. 
- we need to delete all the data and remove all the indexes in it
- to do so, we run the following code

```javascript

// Function to delete all records and then drop all indexes (except _id) from all collections
function deleteAllRecordsAndDropAllIndexes() {
  // Get all the collections in the current database
  const collections = db.getCollectionNames();

  collections.forEach(function(collectionName) {
    // Delete all records from the collection first
    print(`Deleting all records from collection ${collectionName}`);
    db[collectionName].deleteMany({}); // Deletes all documents in the collection

    // Get the indexes of the collection
    const indexes = db[collectionName].getIndexes();
    
    // Drop all indexes except _id
    indexes.forEach(function(index) {
      if (index.name !== "_id_") {
        print(`Dropping index ${index.name} from collection ${collectionName}`);
        db[collectionName].dropIndex(index.name);
      }
    });
  });
  
  print("All records deleted and all indexes (except _id) dropped from all collections.");
}

// Call the function to delete all records and then drop all indexes from all collections
deleteAllRecordsAndDropAllIndexes();
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