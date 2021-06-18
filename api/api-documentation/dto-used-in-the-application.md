---
description: This page aims to list all the DTO used in the Application.
---

# DTO used in the Application

## **ProductDTO**

**ProductDTO is what developers will receive when using a GET request on the product API. The data resembles the same structure as the class object which is stored in the backend and database.**

```text
{
  "id" : 1,
  "name": "string",
  "description": "string",
  "price": 0
}
```

**ProductDTO Schema Detail:**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Key</th>
      <th style="text-align:left">Datatype</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">id</td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">the ID of the product</td>
    </tr>
    <tr>
      <td style="text-align:left">name*</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">the title of the product</td>
    </tr>
    <tr>
      <td style="text-align:left">description*</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">the description describing the category of the product which it falls
        under</td>
    </tr>
    <tr>
      <td style="text-align:left">price*</td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">
        <p>minimum: 0
          <br />maximum: 9999
          <br />default: 0</p>
        <p>the price of the product, accepts a number up to 2 decimal points</p>
      </td>
    </tr>
  </tbody>
</table>

## **CreateProductDTO**

**CreateProductDTO is used to insert a new record into the database.**

```text
{
  "name": "string",
  "description": "string",
  "price": 0
}
```

**CreateProductDTO Schema Detail:**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Key</th>
      <th style="text-align:left">Datatype</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">name*</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">the title of the product</td>
    </tr>
    <tr>
      <td style="text-align:left">description*</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">the description describing the category of the product which it falls
        under</td>
    </tr>
    <tr>
      <td style="text-align:left">price*</td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">
        <p>minimum: 0
          <br />maximum: 9999
          <br />default: 0</p>
        <p>the price of the product, accepts a number up to 2 decimal points</p>
      </td>
    </tr>
  </tbody>
</table>

## **PaginationProductDTO**

**PaginationProductDTO is used when pagination is required for the product records retrieved from the GET Request.**

```text
{
  "name": "string",
  "description": "string",
  "price": 0
}
```

**PaginationProductDTO Schema Detail:**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Key</th>
      <th style="text-align:left">Datatype</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">currentPage*</td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">
        <p>default: 1</p>
        <p>returns the current page</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">itemPerPage*</td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">
        <p>minimum: 10
          <br />maximum: 100
          <br />default: 50</p>
        <p>returns the itemPerPage limit</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">totalItems*</td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">
        <p>default: 1</p>
        <p>returns the total number of items in the records retrieved</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">totalPages*</td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">
        <p>default: 1</p>
        <p>returns the total number of pages created</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">data*</td>
      <td style="text-align:left">ProductDTO</td>
      <td style="text-align:left">retrieve a list of ProductDTO for the current page</td>
    </tr>
  </tbody>
</table>



All data with an asterisk \* basically means the data is not null and required to be initialised with a value at the point of data creation. 

