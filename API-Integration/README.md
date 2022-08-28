# API Integration

## Dynamic API Server

An Express/Node.js based server designed to be a “model agnostic” REST API server, which can perform CRUD operations on any data model

## Business Requirements
We’re opening a online store! In order to support our web application, we need to create an API that will serve specific data (namely, categories and products) to our application. We will write an API to interface with our databases to provide category and product information to our front end app.

As it is highly likely that we will need more data types and sources in the future, it’s imperative that we build this API as a standardized means of working with any data model, using any persistence system, though a common interface. The API Server must operate as follows:

## Support all REST/HTTP methods
- GET: Retrieve record(s) from a data source
    - All
    - One (by id)
    - Some (by filtering)
- POST: Create a new record in a data source
- PUT: Update a single full record in a data source
- PATCH: Update part of a single record in a data source
- DELETE: Delete a record in a data source

Obey a standard routing structure
i.e. http://amazingapi.com/api/v1/products/12345

- /api/v# where # is the version number of our API
    - /model where ‘model’ is the name of the data model to operate on
        - /id where ‘id’ is the id number of a specific entity in the data model

- Allow for Query String parameters for filtering
    - i.e. http://amazingapi.com/api/v1/products?category=electronics
    - This would GET every entry in our products data model where the category is ‘electronics’

Obey a standard output format

- Results will be returned in JSON format
- Results will be served with the correct HTTP header - application/json
- The GET Route, when not retrieving by ID, must return a   full header, with count ,pages, and a results array
- All other routes must return a single object, representing the state of the entity following the operation

## Examples

- GET Records (CRUD: READ)
- GET MANY: http://amazingapi.com/api/v1/products or http://amazingapi.com/api/v1.products?category=electronics

 ```js
  {
    count: 300,
    previous: null,
    next: http://amazingapi.com/api/v1/products?page=2
    results: [
      { name: 'camera', ... },
      { name: 'phone', ... },
      { name: 'tv', ... },
      ...
    ]
  }
  ```

- GET ONE: http://amazingapi.com/api/v1/products/12345

  ```js
  {
    id: 12345,
    name: 'camera',
    manufacturer: 'Nikon',
    model: 'xx435',
    price: 99.99,
    inStock: 2200,
    weight: 1.1
  }
  ```

- POST: http://amazingapi.com/api/v1/products

Create requires that you POST a JSON object to the route that corresponds to the correct model (products, in this case) and returns an object representing what you created:

Request Body:

 ``` js
 {
    id: 12345,
    name: 'camera',
    manufacturer: 'Nikon',
    model: 'xx435',
    price: 99.99,
    inStock: 2200,
    weight: 1.1
  }
  ```

- Output

  ```js
  {
    id: 12345,
    name: 'camera',
    manufacturer: 'Nikon',
    model: 'xx435',
    price: 99.99,
    inStock: 2200,
    weight: 1.1
  }
  ```

- UPDATE Records (CRUD: UPDATE)
- PUT or PATCH: http://amazingapi.com/api/v1/products/12345

Updating records with PUT or PATCH requires a JSON object be given to a route that specifies both the model name and the record ID that represents the record you wish to update. The object given to the route is to be either the FULL object in the case of a PUT, or just the fields you wish to modify, in the case of a PATCH. These operations must always return the object as it exists in the data source after your update operation.

- For example, to change the price:

- PUT Request Body:

  ```js
  {
    id: 12345,
    name: 'camera',
    manufacturer: 'Nikon',
    model: 'xx435',
    price: 109.99,
    inStock: 2200,
    weight: 1.1
  }
  ```

- Output:

```js
  {
    id: 12345,
    name: 'camera',
    manufacturer: 'Nikon',
    model: 'xx435',
    price: 109.99,
    inStock: 2200,
    weight: 1.1
  }
  ```

- PATCH Request Body:

 ```js
  {
    price: 109.99,
  }
  ```

- Output:

  ```js
  {
    id: 12345,
    name: 'camera',
    manufacturer: 'Nikon',
    model: 'xx435',
    price: 109.99,
    inStock: 2200,
    weight: 1.1
  }
  ```

- DELETE Records (CRUD: DELETE)
- DELETE: http://amazingapi.com/api/v1/products/12345

This operation should remove the record with the given ID (12345) from the model (products). The return should be the state of that record in the database following the operation. Convention dictates an empty object be returned rather than null.

Sample Output:

```js
{}
```
