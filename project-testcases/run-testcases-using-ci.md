---
description: >-
  This guide aims to help you to run testcases using github Continuous
  Integration.
---

# Run Testcases using CI

To perform this feature, you will either need to fork this project repository or if u have access to the project's repository you will be able to run testcases using github CI. 

## Running Testcases using Github CI

1.**Navigate to "Actions" tab.**

![fashionshop\_backend root directory in github.](../.gitbook/assets/screenshot-2021-06-16-at-10.10.09-pm%20%281%29.png)

2. **Click on Node.js CI**

![Actions Page in Github](../.gitbook/assets/screenshot-2021-06-16-at-10.12.13-pm.png)

2. **Click on Node.js CI**

![Actions Page in Github](../.gitbook/assets/screenshot-2021-06-16-at-10.12.13-pm.png)

3. **Click on the branch the would like to be run. After clicking on run a new job will appear.**

![Running workflow in Github actions](../.gitbook/assets/screenshot-2021-06-16-at-10.14.28-pm.png)

Pending jobs will be displayed in orange.  Failed jobs will change to red in color and green colored jobs are successful testing.

![](../.gitbook/assets/screenshot-2021-06-16-at-10.15.58-pm.png)



4. We can click on the title to view the details of the successful test on CI.

**Click on "build Backend"**

![Summary of the Job](../.gitbook/assets/screenshot-2021-06-16-at-10.19.41-pm.png)

**Click on "test" to view the outcome**

![View Test Outcome](../.gitbook/assets/screenshot-2021-06-16-at-10.20.01-pm.png)

{% hint style="info" %}
To make changes to the CI build visit the [CI configuration](../configuration/ci-configuration.md) page.
{% endhint %}

