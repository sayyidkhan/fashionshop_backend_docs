---
description: This guide aims to help you to run testcases on this node.js application.
---

# Run Testcases Locally

### Running The Application

**Possible commands to run listed below to start the application:**

```bash
#run the testcases
npm run test

#run the testcases with coverage
npm run test:cov
```

### Running with test Coverage

running with test coverage will produce reports. Sample successful report shown below.

```bash
PASS src/product/product.controller.spec.ts (5.419 s)
PASS src/product/product.service.spec.ts
PASS src/commonUtil/productUtil.spec.ts
PASS src/app.controller.spec.ts
------------------------|---------|----------|---------|---------|---------------------
File                    | % Stmts | % Branch | % Funcs | % Lines | Uncovered Line #s   
------------------------|---------|----------|---------|---------|---------------------
All files               |     100 |    93.06 |     100 |     100 |                     
 src                    |     100 |      100 |     100 |     100 |                     
  app.controller.ts     |     100 |      100 |     100 |     100 |                     
  app.service.ts        |     100 |      100 |     100 |     100 |                     
 src/commonUtil         |     100 |      100 |     100 |     100 |                     
  productUtil.ts        |     100 |      100 |     100 |     100 |                     
 src/product            |     100 |    89.58 |     100 |     100 |                     
  product.controller.ts |     100 |    86.84 |     100 |     100 | 113,226,230,296,300 
  product.service.ts    |     100 |      100 |     100 |     100 |                     
 src/product/dto        |     100 |      100 |     100 |     100 |                     
  createProductDTO.ts   |     100 |      100 |     100 |     100 |                     
  productDTO.ts         |     100 |      100 |     100 |     100 |                     
 src/product/entity     |     100 |      100 |     100 |     100 |                     
  product.entity.ts     |     100 |      100 |     100 |     100 |                     
------------------------|---------|----------|---------|---------|---------------------

Test Suites: 4 passed, 4 total
Tests:       42 passed, 42 total
Snapshots:   0 total
Time:        6.26 s
Ran all test suites.
```



