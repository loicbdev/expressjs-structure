# expressjs-structure

https://blog.logrocket.com/organizing-express-js-project-structure-better-productivity/

<img src="https://imgur.com/IFv6zzP.png" alt="folder structure"/>

Folder structure
In the image above, you will see two main folders: src houses the source code, and test has all the testing code in it. Time to dig a bit deeper into the src subfolders.

First, we have the configs folder, which keeps all the configs needed for the application. For example, if the app connects to a database, the configuration for the database (like database name and username) can be put in a file like db.config.js. Similarly, other configurations like the number of records to show on each page for pagination can be saved in a file named general.config.js inside this configs folder.

The next folder is controllers, which will house all the controllers needed for the application. These controller methods get the request from the routes and convert them to HTTP responses with the use of any middleware as necessary.

Subsequently, the middlewares folder will segregate any middleware needed for the application in one place. There can be middleware for authentication, logging, or any other purpose.

Next up, we have the routes folder that will have a single file for each logical set of routes. For example, there can be routes for one type of resource. It can be further broken down by versions like v1 or v2 to separate the route files by the version of the API.

After that, the models folder will have data models required for the application. This will also depend on the datastore used if it is a relational or a non-relational (NoSQL) database. Contents of this folder will also be defined by the use of an Object Relational Mapping (ORM) library. If an ORM like Sequelize or Prisma is used, this folder will have data models defined as per its requirement.

Consequently, the services folder will include all the business logic. It can have services that represent business objects and can run queries on the database. Depending on the need, even general services like a database can be placed here.

Last but not the least, we have the utils directory that will have all the utilities and helpers needed for the application. It will also act as a place to put shared logic, if any. For example, a simple helper to calculate the offset for a paginated SQL query can be put in a helper.util.js file in this folder.

The test folder has subfolders like unit and integration for unit and integration tests.

The unit folder inside the test folder will have a structure similar to the src folder, as each file in the src folder will need a test, and it is best to follow the same structure, like so:


<img src="https://imgur.com/CyeQhYg.png" alt="folder tests structure"/>

The helper.util.test.js file is placed inside the utils folder in the unit folder. This is the same pattern as in the src folder. In our example project in the next section, we will use Jest to write and run the tests.

Even with this folder structure, some things can be missed. For example, if your project is using RabbitMQ with Node, you will need to keep the publishers and consumers in well-organized folders. Similarly, if you are creating a CLI application to do web scraping with Node, this project structure might be only partially helpful. Having mentioned that, this folder structure will suffice for most API or general web projects that need a better layout.

Also, keep in mind that other files may be needed, like a .env file to keep the secrets safe and different per deployment environment. In the next part, we will look into an example project that follows the structure I have just laid out.
