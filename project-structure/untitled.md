---
description: >-
  this page aims to provide brief description of the project structure and
  framework used for the project.
---

# Software Design

### Technology stack used in this project

* **Nest.JS - Node.Js backend Framework**  


  ![](../.gitbook/assets/image%20%281%29.png)

* **Jest - Node.Js Testcases**  


  ![](../.gitbook/assets/image.png)

* **Swagger - Dynamic API Documentation Generator**  


  ![](../.gitbook/assets/image%20%284%29.png)

* **MySQL - Database used for this project**  


  ![](../.gitbook/assets/image%20%282%29.png)

### Folder Structure For Project

**Folder Structure from src directory**

![Folder Structure for fashionshop](../.gitbook/assets/screenshot-2021-06-16-at-10.55.48-pm.png)

All items related to one table will be stored in one folder with the exception of the "app.\*.ts" files.

**Folder Structure from product folder**

![Folder Structure for product table](../.gitbook/assets/screenshot-2021-06-16-at-10.57.56-pm.png)

Folder structure will be as follows:

* DTO files are stored in the dto directory
* Entity files are stored in the entity directory

**Name of table: product**

|  |  |
| :--- | :--- |
| product.controller.ts | controller layer providing the endpoint API |
| product.module.ts | the file which ties the controller & service files with the main project |
| product.service.ts | the database layer allowing to write queries to retrieving result from database |
| dto/productDTO.ts | data transfer object - it provides form to the data transferred across the network |
| entity/product.entity.ts | entity files are files which define the class object |

### Data Flow from Database to Controller Layer

**General Data Flow**  
  
This is the general high level overview how data flows and passed from each object to another.  
****

![Structure of data flow in this project](../.gitbook/assets/screenshot-2021-06-16-at-11.16.25-pm.png)

**Class Diagram For Product API**

The data flow will be depicted using class **class diagram.**

![class diagram for product api only](../.gitbook/assets/product.jpg)

  
**Class Diagram For Product Pagination API**

\*\*\*\*

