# Protenus Services Coding Challenge

## Introduction

Congratulations! If you've made it this far, odds are we like what we've seen from you :muscle:. The purpose of this 
challenge is to more closely resemble a work-product found in your day-to-day Protenus life. We also feel providing this
as a standalone code repository will allow you to let loose and do what you do best. 

## Problem
For this challenge, you are tasked with augmenting a boilerplate Spring Boot application. The application uses an
embedded H2 RDBMS. No front-end work is required. The tasks are as follows:

#### 1. Create a Domain Entity
Create a simple POJO that will be serialized to the DB. We want to store a *Patient* which should have the following
fields:

 * Id
 * First name
 * Last name
 * Medical record number
 * State (e.g. CA, MD, NY)
 
#### 2. Create Endpoints to Manage Patients
Create a set of endpoints that provide CRUD operations against Patients. We want to access/modify patients in the
following ways:

 * Insert a new patient
 * Modify an existing patient by id
 * View all patients
 * View a patient by id
 
**TIP**: With this completed you should be able to test out your application with a REST tester:

 * POST http://localhost:8080/patients (example URL) for creating a new patient
 * GET  http://localhost:8080/patients for listing patients
 * etc.
 
#### 3. Create a Custom Patient Controller
Create a controller for a custom patient aggregation endpoint. This endpoint should return counts of patients per state.
Example:

```json
[
 { "state": "CA", "count": 3},
 { "state": "MD", "count": 4},
 { "state": "NY", "count": 1}
]
``` 

#### 4. Create a Bulk Patient CSV Upload Endpoint
Finally, add another endpoint to your newly created patient controller. This endpoint should:

 * Accept a CSV file (returning a 400 Bad Request if missing or badly formatted)
 * Insert patient rows found in the CSV into the database
 * Require that a patient row contain a medical record number in order to be inserted (other fields are optional)

## Setup

This project requires Java 17 or greater. We recommend running this application in an IDE such as IntelliJ. This can be
done by creating a Gradle run configuration with the tasks `clean build bootRun`.

## Wrap Up

That's about it! Feel free to add to the code as you see fit (helper classes, add external dependencies, etc.). 

If at any time you have a question about this task, feel free to reach out to one of the development team members. When
you have finished we would like you to **submit your code using the Greenhouse upload link or Dropbox, Google Drive,
etc. (*not* a Git branch/fork).**

**TIP**: It may be helpful to use a file-based DB (specified in `application.yml`) to persist between restarts, as well
as making use of the H2 ui found at http://localhost:8080/h2-console. 