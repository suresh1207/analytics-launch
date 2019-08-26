## Exercise 1.4: Using Adobe's Privacy/GDPR API
In this exercise, the goal is to learn how to use the Adobe Privacy/GDPR API by making use of the UI.

### Learning Objectives

- Learn how to use Adobe's Privacy/GDPR API
- Learn how to use Adobe Launch to implement the client-side Privacy/GDPR JavaScript library
- Understand the process to capture client-side ID's and manually launch a GDPR-request.

### Lab Resources

- Experience Platform UI: [https://platform.adobe.com/](https://platform.adobe.com/)
- Launch: [https://launch-demo.adobe.com/](https://launch-demo.adobe.com/)

### Lab Tasks

- Implement client-side Privacy/GDPR JavaScript using Launch
- Capture ID-data client-side
- Launch a GDPR request

### Story: Using the Privacy/GDPR API through the UI

There are 2 important parts in using the GDPR API:

  * Client-side: Customer Specific ID's need to be captured through a website or mobile application, so that a brand can identify their customer in the Adobe Solutions
  * Server-side: Once a brand has captured a specific customer's online ID's through a client-side implementation, a query can be sent to the Adobe Privacy/GDPR API with these ID's, to either access, control or delete the data related to these ID's.

You need to be able to help La Boutique to understand what they need to do to be fully GDPR-compliant.

### [Exercise 1.4.1 - Implement the Adobe Privacy Extension through Launch](./ex1.md)

In this exercise, you'll implement the Adobe Privacy extension in Launch so that La Boutique is able to retrieve a customer's ID's when this customer wants to enforce his or her rights to access, control or delete their data.

### [Exercise 1.4.2 - Retrieve your specific Adobe ID's](./ex2.md)

In this exercise, you'll retrieve your specific online Adobe ID's with the goal of creating a valid request file.

### [Exercise 1.4.3 - Launch a GDPR Access Request through the GDPR UI](./ex3.md)

In this exercise, you'll take the valid request file from the previous exercise and upload it in the GDPR UI.

[Go Back to Module 1](../README.md)

[Go Back to All Modules](/../../)




