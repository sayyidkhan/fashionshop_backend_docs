---
description: API related to the product pagination API.
---

# Product Pagination API

## Product Pagination API of Each API Endpoint ?

All the pagination API have been abbreviated with **"/pg"** at end of the url to differentiate the difference between using the pagination API.

## How to use Example section ?

If the application is currently running and records are loaded into the database, clicking on an example will cause the web browser to open a new tab and render the API outcome.

An Example is shown here below.

{% hint style="info" %}
**Example:**

[http://localhost:5000/product/pg?currentPage=1&itemPerPage=10](http://localhost:5000/product/pg?currentPage=1&itemPerPage=10
)
{% endhint %}

## Using Swagger API UI to test URL endpoints

Alternatively, to **test the API endpoint** u can [**turn on the Swagger API UI**](../swagger-api/) and **test it directly** with the application. 

{% api-method method="get" host="http://localhost:5000" path="/product/pg" %}
{% api-method-summary %}
Get All Product using Pagination
{% endapi-method-summary %}

{% api-method-description %}
Get all the records with pagination queries which required to be passed.  
  
1. required QUERY\_PARAM {currentPage} -&gt; specify the current page  
2. required QUERY\_PARAM {itemPerPage} -&gt; specify the max item per page  
Available metadata required: \(currentPage , itemPerPage, totalItems, totalPages\)  
Returns a list of ProductDTO object for the current page selected.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="itemPerPage" type="number" required=true %}
specify max number of items per page -&gt; \(min: 10, max:50\)
{% endapi-method-parameter %}

{% api-method-parameter name="currentPage" type="number" required=true %}
specify which page to retrieve
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Returns a PaginationProductDTO with pagination metadata sorted by title from \[ A - Z \]  
Object Received: ProductDTO \[ \]
{% endapi-method-response-example-description %}

```
{
  "currentPage": 1,
  "itemPerPage": 10,
  "totalItems": 501,
  "totalPages": 51,
  "data": [
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
    },
    {
      "id": 186,
      "name": "Ahnya Pants - W",
      "description": "pants",
      "price": 79
    },
    {
      "id": 487,
      "name": "Airchaser Shirt - M",
      "description": "shirts",
      "price": 49
    },
    {
      "id": 354,
      "name": "Airshed Pro Pullover - M",
      "description": "jackets",
      "price": 129
    },
    {
      "id": 55,
      "name": "Airshed Pro Pullover - W",
      "description": "jackets",
      "price": 129
    },
    {
      "id": 175,
      "name": "All Seasons Hemp Canvas Bib Overalls - W",
      "description": "pants",
      "price": 99
    },
    {
      "id": 68,
      "name": "All Seasons Hemp Canvas Chore Coat - W",
      "description": "jackets",
      "price": 129
    }
  ]
}

```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
ERROR: Page number query exceeds available page range
{% endapi-method-response-example-description %}

```

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

[http://localhost:5000/product/pg?currentPage=1&itemPerPage=10](http://localhost:5000/product/pg?currentPage=1&itemPerPage=10
)
{% endhint %}

{% api-method method="get" host="http://localhost:5000" path="/product/pg/sortby" %}
{% api-method-summary %}
Get All Products + Sorting with pagination
{% endapi-method-summary %}

{% api-method-description %}
Get all the records with pagination queries which required to be passed with optional sorting param query to be passed.  
  
\#\#\# Required Parameters \#\#\#  
1. required QUERY\_PARAM {currentPage} -&gt; specify the current page  
2. required QUERY\_PARAM {itemPerPage} -&gt; specify the max item per page  
Available metadata returned: \(currentPage, itemPerPage, totalItems, totalPages\)  
returns a list of ProductDTO object for the current page selected  
  
\#\#\# Optional Parameters \#\#\#  
3. optional to pass {orderByName} -&gt; if passed as PARAM\_QUERY will sort based on possible values  
4. optional to pass {orderByPrice} -&gt; if passed as PARAM\_QUERY will sort based on possible values  
5. if multiple sort is specified, then it will be sorted by name then price.  
6. if other values is provided to orderByName / orderByPrice, it will disregard the value and sort it in ascending order.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="itemPerPage" type="number" required=true %}
specify max number of items per page -&gt; \(min: 10, max:50\)
{% endapi-method-parameter %}

{% api-method-parameter name="currentPage" type="number" required=true %}
specify which page to retrieve
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
Displays a list of all the products from the database sorted by choice\(s\) selected  
Object Received: ProductPaginationDTO \[ \]
{% endapi-method-response-example-description %}

```
{
  "currentPage": 1,
  "itemPerPage": 10,
  "totalItems": 501,
  "totalPages": 51,
  "data": [
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
    },
    {
      "id": 186,
      "name": "Ahnya Pants - W",
      "description": "pants",
      "price": 79
    },
    {
      "id": 487,
      "name": "Airchaser Shirt - M",
      "description": "shirts",
      "price": 49
    },
    {
      "id": 354,
      "name": "Airshed Pro Pullover - M",
      "description": "jackets",
      "price": 129
    },
    {
      "id": 55,
      "name": "Airshed Pro Pullover - W",
      "description": "jackets",
      "price": 129
    },
    {
      "id": 175,
      "name": "All Seasons Hemp Canvas Bib Overalls - W",
      "description": "pants",
      "price": 99
    },
    {
      "id": 68,
      "name": "All Seasons Hemp Canvas Chore Coat - W",
      "description": "jackets",
      "price": 129
    }
  ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
ERROR: Page number query exceeds available page range
{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
No Product Found, No Record In Database
{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="info" %}
**Example:**

[http://localhost:5000/product/pg/sortby?orderByName=asc&currentPage=1&itemPerPage=10](http://localhost:5000/product/pg/sortby?orderByName=asc&currentPage=1&itemPerPage=10
)
{% endhint %}

{% api-method method="get" host="http://localhost:5000" path="/product/pg/filterByPrice" %}
{% api-method-summary %}
Get Products by filtering price + sorting with pagination
{% endapi-method-summary %}

{% api-method-description %}
get products by filtering price \(within min - max range\) or \(&gt;= min\) or \(&lt;= max\) then sorting with pagination  
  
\#\#\# required Parameters \#\#\#  
1. required QUERY\_PARAM {currentPage} -&gt; specify the current page  
2. required QUERY\_PARAM {itemPerPage} -&gt; specify the max item per page  
Available metadata returned: \(currentPage, itemPerPage, totalItems, totalPages\)  
returns a list of ProductDTO object for the current page selected  
  
\#\#\# optional Parameters \#\#\#  
3. {minprice} - OPTIONAL\_PARAMETER, query will still work w/o min price input  
4. {maxprice\) - OPTIONAL\_PARAMETER, query will still work w/o max price input  
5. optional to pass {orderByName} -&gt; query will still work w/o inputing min or max value  
6. optional to pass {orderByPrice} -&gt; query will still work w/o input min or max value   
7. if multiple sort is specified, then it will be sorted by name then price.  
8. if other values is provided to orderByName / orderByPrice, it will disregard the value and sort it in ascending order.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="itemPerPage" type="string" required=true %}
specify the max item per page \(min: 10, max: 50\)
{% endapi-method-parameter %}

{% api-method-parameter name="currentPage" type="number" required=true %}
specify which page to retrieve
{% endapi-method-parameter %}

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
Object Received: ProductPaginationDTO \[ \]
{% endapi-method-response-example-description %}

```
{
  "currentPage": 1,
  "itemPerPage": 10,
  "totalItems": 2,
  "totalPages": 1,
  "data": [
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
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
ERROR - Min price greater than or equal to Max price. or ERROR: Page number query exceeds available page range.
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

[http://localhost:5000/product/pg/filterByPrice?minprice=10&maxprice=20&orderByPrice=asc&currentPage=1&itemPerPage=10](http://localhost:5000/product/pg/filterByPrice?minprice=10&maxprice=20&orderByPrice=asc&currentPage=1&itemPerPage=10
)
{% endhint %}

{% api-method method="get" host="http://localhost:5000" path="/product/pg/filterByName/{name}" %}
{% api-method-summary %}
Get Products by filtering name + sorting with pagination
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
Object Received: ProductPaginationDTO \[ \]
{% endapi-method-response-example-description %}

```
{
  "currentPage": 1,
  "itemPerPage": 10,
  "totalItems": 30,
  "totalPages": 3,
  "data": [
    {
      "id": 107,
      "name": "Organic Cotton Spring Sweater Tank - W",
      "description": "sweaters",
      "price": 79
    },
    {
      "id": 19,
      "name": "Better Sweater Vest - W",
      "description": "jackets",
      "price": 99
    },
    {
      "id": 328,
      "name": "Better Sweater 1/4 Zip - M",
      "description": "jackets",
      "price": 99
    },
    {
      "id": 332,
      "name": "Better Sweater Vest - M",
      "description": "jackets",
      "price": 99
    },
    {
      "id": 460,
      "name": "Fog Cutter Sweater - M",
      "description": "sweaters",
      "price": 99
    },
    {
      "id": 1,
      "name": "Better Sweater 1/4-Zip - W",
      "description": "jackets",
      "price": 99.1
    },
    {
      "id": 31,
      "name": "Lightweight Better Sweater Marsupial Pullover - W",
      "description": "jackets",
      "price": 119
    },
    {
      "id": 106,
      "name": "Long-Sleeved Organic Cotton Spring Sweater - W",
      "description": "sweaters",
      "price": 119
    },
    {
      "id": 392,
      "name": "Better Sweater Rib Knit 1/4-Zip - M",
      "description": "jackets",
      "price": 119
    },
    {
      "id": 435,
      "name": "Better Sweater Henley Pullover - M",
      "description": "fleece",
      "price": 119
    }
  ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Error: Page number query exceeds available page range.
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

[http://localhost:5000/product/pg/filterByName/sweater?orderByPrice=asc&currentPage=1&itemPerPage=10](http://localhost:5000/product/pg/filterByName/sweater?orderByPrice=asc&currentPage=1&itemPerPage=10
)
{% endhint %}



For checking the **object structure\(DTO\)** that was sent or received via API, do check the [DTO used in the Application page.](dto-used-in-the-application.md)

