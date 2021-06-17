# Product API

## Product API

All fields are optional. New fiddle setting will be used if no data provided.

{% api-method method="get" host="http://localhost:5000" path="/product" %}
{% api-method-summary %}
Get All Product
{% endapi-method-summary %}

{% api-method-description %}
No parameters are required to be passed in order to use this API.  
An API which helps to get all the products from the product's table.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Returns a list of productDTO  
Object Received: ProductDTO \[ \]
{% endapi-method-response-example-description %}

```
[
  {
    "id": 477,
    "name": "A/C Shirt - M",
    "description": "shirts",
    "price": 79
  },
  {
    "id": 311,
    "name": "Active Briefs - W",
    "description": "bras",
    "price": 24
  },
  {
    "id": 312,
    "name": "Active Hipster - W",
    "description": "bras",
    "price": 24
  },
  {
    "id": 308,
    "name": "Active Mesh Bra - W",
    "description": "bras",
    "price": 45
  }
]
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="info" %}
**Example:**

[http://localhost:5000/product](http://localhost:5000/product)
{% endhint %}

{% api-method method="post" host="http://localhost:5000" path="/product" %}
{% api-method-summary %}
Insert A New Product Listing
{% endapi-method-summary %}

{% api-method-description %}
Insert a new product object that needs to be added to the product listing, no parameters required to be passed.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="Request Body" type="object" required=true %}
Insert a new record into product table.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
Returns a the new productDTO object  
Object Received: ProductDTO
{% endapi-method-response-example-description %}

```
{
  "id": 501,
  "name": "string",
  "description": "string",
  "price": "0.00"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
No Product\(s\) Found
{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

**Example Value \| Schema \(Request Body which is required to be passed\)**

**Schema Used: CreateProductDTO**

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

{% hint style="info" %}
**Example:**

[http://localhost:5000/product](http://localhost:5000/product)
{% endhint %}

{% api-method method="get" host="http://localhost:5000" path="/product/sortby" %}
{% api-method-summary %}
Get All Products + Sorting
{% endapi-method-summary %}

{% api-method-description %}
1. optional to pass {orderByName} -&gt; if passed as PARAM\_QUERY will sort based on possible values  
2. optional to pass {orderByPrice} -&gt; if passed as PARAM\_QUERY will sort based on possible values  
3. if multiple sort is specified, then it will be sorted by name then price.  
4. if other values is provided to orderByName / orderByPrice, it will disregard the value and sort it in ascending order.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="orderByPrice" type="string" required=false %}
Accepts  
`asc` sort by Ascending Order  
`desc` sort by Descending Order
{% endapi-method-parameter %}

{% api-method-parameter name="orderByName" type="string" required=false %}
Accepts  
`asc` sort by Ascending Order  
****`desc` ****sort by ****Descending Order
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Displays a list of all the products from the database sorted by choice\(s\) selected  
Object Received: ProductDTO \[\]
{% endapi-method-response-example-description %}

```
[
  {
    "id": 477,
    "name": "A/C Shirt - M",
    "description": "shirts",
    "price": 79
  },
  {
    "id": 311,
    "name": "Active Briefs - W",
    "description": "bras",
    "price": 24
  },
  {
    "id": 312,
    "name": "Active Hipster - W",
    "description": "bras",
    "price": 24
  }
]
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="info" %}
**Example:**

[http://localhost:5000/product/sortby?orderByPrice=asc](http://localhost:5000/product/sortby?orderByPrice=asc)
{% endhint %}

{% api-method method="get" host="http://localhost:5000" path="/filterById/{id}" %}
{% api-method-summary %}
Get One Product by ID Only
{% endapi-method-summary %}

{% api-method-description %}
get one product by ID, only numbers\(integer\) are accepted. If product ID does not exist, it will return 404 error. Currently data preparation ID's are \(1 - 500\) are valid records. ID 501 and later does not exist unless added. Can use these data for data testing scenarios. 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="number" required=true %}
any number from one to infinity -&gt; possible values: \( 1 ... n \)the product
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Return 1 productDTO successfully which was searched by ID.  
Object Received: ProductDTO
{% endapi-method-response-example-description %}

```
{
  "id": 20,
  "name": "Micro Puff Jacket - W",
  "description": "jackets",
  "price": 249
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
No Product\(s\) Found.
{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="info" %}
**Example:**

[http://localhost:5000/product/filterById/20](http://localhost:5000/product/filterById/20)
{% endhint %}



{% api-method method="get" host="http://localhost:5000" path="/filterByPrice" %}
{% api-method-summary %}
Get Products by filtering price + sorting
{% endapi-method-summary %}

{% api-method-description %}
get products by filtering price \(within min - max range\) or \(&gt;= min\) or \(&lt;= max\) then sorting  
1. {minprice} - OPTIONAL\_PARAMETER, query will still work w/o min price input  
2. {maxprice\) - OPTIONAL\_PARAMETER, query will still work w/o max price input  
3. optional to pass {orderByName} -&gt; query will still work w/o inputing min or max value  
4. optional to pass {orderByPrice} -&gt; query will still work w/o input min or max value   
5. if multiple sort is specified, then it will be sorted by name then price.  
6. if other values is provided to orderByName / orderByPrice, it will disregard the value and sort it in ascending order.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="minprice" type="number" required=false %}
minimum price - cannot be less than 0
{% endapi-method-parameter %}

{% api-method-parameter name="maxprice" type="number" required=false %}
max maximum price - cannot be more than 9999 
{% endapi-method-parameter %}

{% api-method-parameter name="orderByPrice" type="string" required=false %}
Accepts  
`asc` sort by Ascending Order  
`desc` sort by Descending Order
{% endapi-method-parameter %}

{% api-method-parameter name="orderByName" type="string" required=false %}
Accepts  
`asc` sort by Ascending Order  
****`desc` ****sort by ****Descending Order
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Displays a list of all the products from the database with price filter\(s\) + sorted by choice\(s\) selected.  
Object Received: ProductDTO \[ \]
{% endapi-method-response-example-description %}

```
[
  {
    "id": 314,
    "name": "Sender Hipster - W",
    "description": "bras",
    "price": 18
  },
  {
    "id": 315,
    "name": "Sender Briefs - W",
    "description": "bras",
    "price": 18
  }
]
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
ERROR - Min price greater than or equal to Max price.
{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
No Product\(s\) found.
{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="info" %}
**Example:**

[http://localhost:5000/product/filterByPrice?minprice=10&maxprice=20](http://localhost:5000/product/filterByPrice?minprice=10&maxprice=20)
{% endhint %}

{% api-method method="get" host="http://localhost:5000" path="/filterByName/{name}" %}
{% api-method-summary %}
Get Products by filtering name + sorting
{% endapi-method-summary %}

{% api-method-description %}
get products by filtering name using the like clause + sorting  
1. {name\) - REQUIRED PARAMETER, query will search for name of product and returns the product name which has the text name in it  
2. optional to pass {orderByName} -&gt; query will still work w/o inputing min or max value  
3. optional to pass {orderByPrice} -&gt; query will still work w/o input min or max value   
4. if multiple sort is specified, then it will be sorted by name then price.  
5. if other values is provided to orderByName / orderByPrice , it will disregard the value and sort it in ascending order.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="name" type="string" required=true %}
name of the product -&gt; will be filtered using like clause
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-query-parameters %}
{% api-method-parameter name="orderByPrice" type="string" required=false %}
Accepts  
`asc` sort by Ascending Order  
`desc` sort by Descending Order
{% endapi-method-parameter %}

{% api-method-parameter name="orderByName" type="string" required=false %}
Accepts  
`asc` sort by Ascending Order  
****`desc` ****sort by ****Descending Order
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Displays a list of all the products from the database with price filter\(s\) + sorted by choice\(s\) selected.  
Object Received: ProductDTO \[ \]
{% endapi-method-response-example-description %}

```
[
  {
    "id": 1,
    "name": "Better Sweater 1/4-Zip - W",
    "description": "jackets",
    "price": 99.1
  },
  {
    "id": 2,
    "name": "Better Sweater Jacket - W",
    "description": "jackets",
    "price": 139.2
  },
  {
    "id": 8,
    "name": "Down Sweater - W",
    "description": "jackets",
    "price": 229
  },
  {
    "id": 17,
    "name": "Down Sweater Hoody - W",
    "description": "jackets",
    "price": 279
  }
]
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
No Product\(s\) found.
{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="info" %}
**Example:**

[http://localhost:5000/product/filterByName/sweater](http://localhost:5000/product/filterByName/sweater)
{% endhint %}



For checking the **object structure\(DTO\)** that was sent or received via API, do check the [DTO used in the Application page.](dto-used-in-the-application.md)

