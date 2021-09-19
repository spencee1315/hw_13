# Object-Relational Mapping (ORM): E-Commerce Back End - Homework 13, UW Coding Bootcamp

![Github licence](http://img.shields.io/badge/license-MIT-blue.svg)

## Description

For week 13 of the UW Coding Bootcamp my homework invited me to build the back end to an E-Commerce Site by modifying starter code. This application uses Express.js API and Sequelize to interact with a MySQL database. This application displays the creation of a database using MySQL with models and associations. Then it demonstrates the API Routes to perform RESTful CRUD operations displayed in my walk through videos, provided below. 


## User Story

```md
AS A manager at an internet retail company
I WANT a back end for my e-commerce website that uses the latest technologies
SO THAT my company can compete with other e-commerce companies
```

## Built With

* [MySQL](https://www.mysql.com/)
* [Sequelize](https://sequelize.org/)
* [Express.js](https://expressjs.com/)
* [Open Weather Map API](https://api.openweathermap.org)
* [Developer Mozilla](https://developer.mozilla.org)

## Link to GitHub Repo

* [See Live Site](https://github.com/spencee1315/hw_13)

## Installation 
The user should clone the repository from GitHub. This application requires Node.js, Express.js, and Sequelize. To connect to the database run `mysql -u root -p` and enter password from .env file. Then source the schema.sql. To seed the file run `npm run seed`. Finally to connect to the server run `npm start`. 

## Usage 
This application will allow users to view, add, edit, and delete categories, products, and tags.

View video to see MySQL walk through via [Screencastify]()<br>
View video to walk through of the API routes. [Screencastify]()<br>
View video to see Insomnia walk through via [Screencastify]()

## License 
This project is license under MIT

## Contributing 
Contributors should read the installation section. 

## Tests
There are no tests for this application

## Code Snippet
This a code snippet from the Model, index.js file...........

```javascript
// import models
const Product = require('./Product');
const Category = require('./Category');
const Tag = require('./Tag');
const ProductTag = require('./ProductTag');

// Products belongsTo Category
Product.belongsTo(Category, {
  foreignKey: 'category_id'
});

// Categories have many Products
Category.hasMany(Product, {
  foreignKey: 'category_id',
  onDelete: 'SET NULL'
})

// Products belongToMany Tags (through ProductTag)
Product.belongsToMany(Tag, {
  through: ProductTag,
  // as: 'product_tag',
  foreignKey: 'product_id'
})

// Tags belongToMany Products (through ProductTag)
Tag.belongsToMany(Product, {
  through: ProductTag,
  // as: 'product_tag',
  foreignKey: 'tag_id'
})

module.exports = {
  Product,
  Category,
  Tag,
  ProductTag,
};
```

### Authors

* **Elliott Spencer**

### Contact Information

* [Link to Portfolio Site](https://spencee1315.github.io/hw_wk2/)

* [Link to Github](https://github.com/spencee1315)

* [Link to LinkedIn](https://www.linkedin.com/in/elliott-spencer-886a9818/)
