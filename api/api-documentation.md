# API Documentation

## API Endpoints Overview

For this project the API endpoints have been broken down into two API endpoints and are listed below.

* product API endpoints
* product pagination API endpoint

## Product API Endpoints

All fields are optional. New fiddle setting will be used if no data provided.

{% api-method method="get" host="https://jsfiddle.net" path="/api/post/:framework/:version/dependencies/:dependency\_list/" %}
{% api-method-summary %}

{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-form-data-parameters %}
{% api-method-parameter name="normalize\_css" type="string" required=false %}
`yes` or `no` - should `normalize.css` be loaded
{% endapi-method-parameter %}

{% api-method-parameter name="wrap" type="string" required=false %}
Set the JS code wrap:  
  
Accepts:  
  
- `l` for `onload`  
- `d` for `domready`  
- `h` for no wrap at bottom of `HEAD`  
- `b` for no wrap at bottom of `BODY`
{% endapi-method-parameter %}

{% api-method-parameter name="html" type="string" required=false %}
code for the HTML panel
{% endapi-method-parameter %}

{% api-method-parameter name="css" type="string" required=false %}
code for the CSS panel
{% endapi-method-parameter %}

{% api-method-parameter name="js" type="string" required=false %}
code for the JS panel
{% endapi-method-parameter %}

{% api-method-parameter name="html\_panel" type="integer" required=false %}
language for the HTML panel.  
  
Accepts `0` only.
{% endapi-method-parameter %}

{% api-method-parameter name="css\_panel" type="integer" required=false %}
language for the CSS panel.  
  
Accepts:  
- `0` for **CSS**  
- `1` for **SCSS**
{% endapi-method-parameter %}

{% api-method-parameter name="js\_panel" type="integer" required=false %}
language for the JS panel  
  
Accepts:  
- `0` for **JavaScript**  
- `1` for **CoffeeScript**  
- `2` for **JavaScript 1.7**  
- `3` for 
{% endapi-method-parameter %}

{% api-method-parameter name="title" type="string" required=false %}
Title of the fiddle
{% endapi-method-parameter %}

{% api-method-parameter name="description" type="string" required=false %}
Description of the fiddle
{% endapi-method-parameter %}

{% api-method-parameter name="dtd" type="string" required=false %}
Documents definition type.  
  
Accepts a substring of the chosen DTD \(ie `html 4`\).  
{% endapi-method-parameter %}

{% api-method-parameter name="resources" type="string" required=false %}
a comma separated list of external resources
{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="info" %}
**Example:**

[http://jsfiddle.net/3Lwgk4c5/](http://jsfiddle.net/3Lwgk4c5/)
{% endhint %}

