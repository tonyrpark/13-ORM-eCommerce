## Object-Relational Mapping (ORM) Challenge: E-commerce Back End

### Description & Task

Internet retail, also known as **e-commerce**, is the largest sector of the electronics industry, generating an estimated $29 trillion in 2019. E-commerce platforms like Shopify and WooCommerce provide a suite of services to businesses of all sizes. Due to their prevalence, understanding the fundamental architecture of these platforms will benefit you as a full-stack web developer.

Your task is to build the back end for an e-commerce site by modifying starter code. You’ll configure a working Express.js API to use Sequelize to interact with a MySQL database.

Because this application won’t be deployed, you’ll also need to provide a link to a walkthrough video that demonstrates its functionality and all of the acceptance criteria being met. You’ll need to submit a link to the video and add it to the readme of your project.

### App Demo

- Code with Schema Incorporated and Initial 'npm start' command

![Code](./Assets/e-Commerce%20HW%20Assets/code.gif)

- MySQL GIF

![mySQL](./Assets/e-Commerce%20HW%20Assets/mySQL.gif)

- GET request

![getRequest](./Assets/e-Commerce%20HW%20Assets/getRequestAll.gif)

- POST request

![postRequest](./Assets/e-Commerce%20HW%20Assets/postRequest.gif)
![categoryPostRequest](./Assets/e-Commerce%20HW%20Assets/categoryPostRequest.gif)

- Put Request

![putRequest](./Assets/e-Commerce%20HW%20Assets/putRequest.gif)

- Delete Request

![deleteRequest](./Assets/e-Commerce%20HW%20Assets/deleteRequest.gif)

![](images/demo-5.gif)

### User Story

```text
AS A manager at an internet retail company
I WANT a back end for my e-commerce website that uses the latest technologies
SO THAT my company can compete with other e-commerce companies
```

### Acceptance Criteria

```md
GIVEN a functional Express.js API
WHEN I add my database name, MySQL username, and MySQL password to an environment variable file
THEN I am able to connect to a database using Sequelize
WHEN I enter schema and seed commands
THEN a development database is created and is seeded with test data
WHEN I enter the command to invoke the application
THEN my server is started and the Sequelize models are synced to the MySQL database
WHEN I open API GET routes in Insomnia Core for categories, products, or tags
THEN the data for each of these routes is displayed in a formatted JSON
WHEN I test API POST, PUT, and DELETE routes in Insomnia Core
THEN I am able to successfully create, update, and delete data in my database
```

### Database Models

- `Category`

  - `id`

    - Integer
    - Doesn't allow null values
    - Set as primary key
    - Uses auto increment

  - `category_name`
    - String
    - Doesn't allow null values

- `Product`

  - `id`

    - Integer
    - Doesn't allow null values
    - Set as primary key
    - Uses auto increment

  - `product_name`

    - String
    - Doesn't allow null values

  - `price`

    - Decimal
    - Doesn't allow null values
    - Validates that the value is a decimal

  - `stock`

    - Integer
    - Doesn't allow null values
    - Set a default value of 10
    - Validates that the value is numeric

  - `category_id`
    - Integer
    - References the category model's id

- `Tag`

  - `id`

    - Integer
    - Doesn't allow null values
    - Set as primary key
    - Uses auto increment

  - `tag_name`
    - String

- `ProductTag`

  - `id`

    - Integer
    - Doesn't allow null values
    - Set as primary key
    - Uses auto increment

  - `product_id`

    - Integer
    - References the product model's id

  - `tag_id`
    - Integer
    - References the tag model's id

### Associations

_You'll need to execute association methods on your Sequelize models to create the following relationships between them:_

- Product belongs to Category, as a category can have multiple products but a product can only belong to one category.

- Category has many Product models.

- Product belongs to many Tag models. Using the ProductTag through model, allow products to have multiple tags and tags to have many products.

- Tag belongs to many Product models.

### Instructions on how to run the app

- Add a .env file to the root of the app with the following details

```text
DB_NAME='ecommerce_db'
DB_USER='root'
DB_PW='xxxx'
```

Tony Park 2021
