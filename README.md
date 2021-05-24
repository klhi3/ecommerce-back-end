# E-Commerce Back End

This **e-commerce** is to build the back end for an e-commerce site with Express.js API to use Sequelize to interact with a MySQL database based on Object-Relational Mapping (ORM).   
It will not be deployed but provide functionality and all of the acceptance criteria being met. 
This contains the video and add it to the readme of the project. 

## Features

This is a back end for the e-commerce website that use Express.js API

1) add the database name, MySQL username, and MySQL password to an environment variable file
2) `schema.sql` file in the `db` folder to create your database with MySQL shell commands
3) connect to a database using Sequelize
4) enter schema and seed commands
5) create a development database and is seeded with test data
6) run the command to invoke the application : npm start
7) the server is started and the Sequelize models are synced to the MySQL database
8) open API GET routes in Insomnia Core for categories, products, or tags
9) the data for each of these routes is displayed in a formatted JSON
10) test API POST, PUT, and DELETE routes in Insomnia Core
11) able to successfully create, update, and delete data in the database ecommerce_db


## Portfolio


* ![“how to create the schema from the MySQL shell”](../assets/images/page.gif)

* !["how to seed the database from the command line”](../assets/images/page1.gif)

* ![how to start the application’s server”](../assets/images/page2.gif)

* ![GET routes for all categories, all products, and all tags being tested in Insomnia Core : GET tags,” “GET Categories,” and “GET All Products”](../assets/images/page3.gif)

* ![GET routes for a single category, a single product, and a single tag being tested in Insomnia Core: “GET tag by id,” “GET Category by ID,” and “GET One Product”](../assets/images/page4.gif)

* ![POST, PUT, and DELETE routes for categories, products, and tags being tested in Insomnia Core: “DELETE Category by ID,” “CREATE Category,” and “UPDATE Category.””](../assets/images/page5.gif)


## Links

* ![MySQL2](https://www.npmjs.com/package/mysql2) and ![Sequelize](https://www.npmjs.com/package/sequelize) packages to connect your Express.js API to a MySQL database 
* ![dotenv](https://www.npmjs.com/package/dotenv) package to use environment variables to store sensitive data.
 

### Database Models

* `Category`

  * `id`

    * Integer.
  
    * Doesn't allow null values.
  
    * Set as primary key.
  
    * Uses auto increment.

  * `category_name`
  
    * String.
  
    * Doesn't allow null values.

* `Product`

  * `id`
  
    * Integer.
  
    * Doesn't allow null values.
  
    * Set as primary key.
  
    * Uses auto increment.

  * `product_name`
  
    * String.
  
    * Doesn't allow null values.

  * `price`
  
    * Decimal.
  
    * Doesn't allow null values.
  
    * Validates that the value is a decimal.

  * `stock`
  
    * Integer.
  
    * Doesn't allow null values.
  
    * Set a default value of `10`.
  
    * Validates that the value is numeric.

  * `category_id`
  
    * Integer.
  
    * References the `Category` model's `id`.

* `Tag`

  * `id`
  
    * Integer.
  
    * Doesn't allow null values.
  
    * Set as primary key.
  
    * Uses auto increment.

  * `tag_name`
  
    * String.

* `ProductTag`

  * `id`

    * Integer.

    * Doesn't allow null values.

    * Set as primary key.

    * Uses auto increment.

  * `product_id`

    * Integer.

    * References the `Product` model's `id`.

  * `tag_id`

    * Integer.

    * References the `Tag` model's `id`.

### Associations

execute association methods on the  Sequelize models to create the following relationships between them:

* `Product` belongs to `Category`, and `Category` has many `Product` models, as a category can have multiple products but a product can only belong to one category.

* `Product` belongs to many `Tag` models, and `Tag` belongs to many `Product` models. Allow products to have multiple tags and tags to have many products by using the `ProductTag` through model.


### API Routes to Perform RESTful CRUD Operations

`product-routes.js`, `tag-routes.js`, and `category-routes.js` to perform create, read, update, and delete operations using the Sequelize models.

### Seed the Database : `npm run seed` 

### Sync Sequelize to the Database on Server Start :  `server.js` 
