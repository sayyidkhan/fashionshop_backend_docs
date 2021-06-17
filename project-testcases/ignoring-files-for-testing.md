---
description: Ignoring Specific files for Test Suites
---

# Ignoring files For testing

### Ignoring Specific files for Test Suites

Ignoring specific files for test suites have benefits as we do not want to be testing redundant code or testing a code with the intention of just testing the code without testing the functionality.  
  
Navigate to the package.json, here we have the jest configuration. we have added the files which we would like to ignore in the "coveragePathIgnorePatterns", so that they will not be added into the project

```javascript
"jest": {
    "moduleFileExtensions": [
      "js",
      "json",
      "ts"
    ],
    "rootDir": "src",
    "testRegex": ".*\\.spec\\.ts$",
    "transform": {
      "^.+\\.(t|j)s$": "ts-jest"
    },
    /* add or remove file here */
    "coveragePathIgnorePatterns" : [
      "<rootDir>/database_init.ts",
      "<rootDir>/main.ts"
    ],
    /* add or remove file here */
    "collectCoverageFrom": [
      "**/*.(t|j)s"
    ],
    "coverageDirectory": "../coverage",
    "testEnvironment": "node"
  }
```



