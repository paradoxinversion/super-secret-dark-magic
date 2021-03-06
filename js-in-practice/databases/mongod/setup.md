Setting up Mongo Connections in Node

The following snippet can be imported and run

```javaScript
export async function connectToDatabase() {
  try {
    const connection = await mongoose.connect(process.env.DATABASE_URI, {
      useNewUrlParser: true,
      useUnifiedTopology: true,
      serverSelectionTimeoutMS: 5000,
    });

    // We'll return the connection if it's successful.
    return connection;
  } catch (e) {
    switch (e.name) {
      // Some very simple error handling-- Here we're just checking if the server can't be found
      case "MongooseServerSelectionError":
        console.log(
          "DB Connection to the DB failed-- double check DATABASE_URI and ensure remote or local database is reachable"
        );
        throw e;

      default:
        console.log(
          "Something went wrong while trying to connect to the database."
        );
        throw e;
    }
  }
}
```
