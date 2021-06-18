---
description: >-
  This page aims to guide you on the setup or changes in the swagger
  configuration.
---

# Swagger API Setup

## Swagger Config

there is only two places which the configuration of swagger is setup in this project.

* src/main.ts - store the setup config files
* [config/default.js](../../configuration/project-config.md#swaggeroptions) - stores metadata to start swagger

##  Main.ts File

Swagger API setup codes are only stored in this file and not anywhere else in the project. Do not remove these codes otherwise swagger will no longer exist in the project.

```javascript
  /* swagger config */
  const options = new DocumentBuilder()
      .setTitle(config.swaggerOptions.title)
      .setDescription(config.swaggerOptions.description)
      .setVersion(config.swaggerOptions.version)
      .addTag(config.swaggerOptions.product_api)
      .addTag(config.swaggerOptions.pagination_api)
      .build();
  const document = SwaggerModule.createDocument(app,options, {
    /* add your modules here to list your API dynamically in the project */
    include : [ProductModule],
  });
  SwaggerModule.setup(config.swaggerOptions.swagger_api_url,app,document);
```

{% hint style="info" %}
 Data to set title, description and etc.. is obtained from [config/default.js](../../configuration/project-config.md#swaggeroptions) file.
{% endhint %}

If a new module is created but does not appear in the Swagger API, do add it into the include key-value pair.

{% code title="main.ts" %}
```javascript
const document = SwaggerModule.createDocument(app,options, {
    /* add your modules here to list your API dynamically in the project */
    include : [ProductModule , YourNewModuleHere ],
  });
```
{% endcode %}



