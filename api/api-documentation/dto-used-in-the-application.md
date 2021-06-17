---
description: This page aims to list all the DTO used in the Application.
---

# DTO used in the Application

## **Schema Used: ProductDTO**

```text
{
  "id" : 1,
  "name": "string",
  "description": "string",
  "price": 0
}
```

**ProductDTO**

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

## **Schema Used: CreateProductDTO**

```text
{
  "name": "string",
  "description": "string",
  "price": 0
}
```

**CreateProductDTO**

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



\*\*\*\*

