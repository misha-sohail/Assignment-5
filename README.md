**Overview**
This project demonstrates automated API testing using Apache JMeter.

The main focus is to cover CRUD operations (Create, Read, Update, Delete) on an API endpoint, validate the full workflow, and use data-driven testing with a CSV file.

The test plan is designed to chain requests together, extract values dynamically, and verify each step using assertions and JMeter listeners.

All project files required for submission—including the JMeter test plan and CSV test data—are organized for ease of review and replication.

Test Plan Structure and Sequence
Uses a single Thread Group to define user and loop count.

Contains HTTP Request samplers for:

POST (user creation using CSV data).

GET (retrieves user details using the ID extracted from POST).

PUT or PATCH (updates user data).

DELETE (removes the created user).

GET again (checks if the user is deleted and expects a 404 or empty response).

A CSV Data Set Config reads user information from the CSV file for the POST request.

JSON Extractor post-processor captures the ID from the POST response to use in subsequent requests.

Each request includes appropriate response assertions:

Check for success keywords, status codes (201, 200, 204), or a 404 on final GET.

Includes listeners for:

"View Results Tree" for detailed step-by-step debugging.

"Summary Report" for overall test results.

"View Results in Table" for structured outputs.

**Data File Example:**
The CSV file, users.csv, must be comma-separated and include all columns needed:
name,email,age,email_update

**How to Execute the Project:**
Download and extract the repository files, keeping all folders intact.

Open api_crud_test.jmx in JMeter.

Check and update the CSV file path in the test plan if necessary.

Press the Start button to run the full test scenario.

Review test results in the preconfigured listeners.

**Validation and Results:**
All steps must pass with expected codes and confirmations:

Successful user creation (POST).

User data retrieved and updated (GET and PUT/PATCH).

User deletion (DELETE).

Final GET fails as expected (404/empty).
