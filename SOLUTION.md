# Solutions

## 1. "An accurately described JIRA ticket with whatever information you think is necessary."
Story: Complex property service (CPS) tests   

Sub-tasks for the story:
* Test merchant property flow
* Test point of sale property flow
* Test merchant status impact on previous scenarios

Author is taking "Lean" approach and keeps document footprint minimal unless extra information is necessary by someone else involved in the project.
Extra description for tests is added in the code by using Allure reporting framework so that tests steps and data are clear for tests to be transparent. 

## 2. "Describe the test tools you would use and why, for example, SoapUI, Gherkin, Postman, JMeter, etc."
Author would use custom made test framework written in some of JVM-based language (preferrably Kotlin) with following properties:
* build system - Gradle
* test framework - TestNG
* reporting framework - Allure
* web testing framework - Selenium
* API communication framework - OkHttp
* OpenAPI specification verificator - Library "com.atlassian.oai:swagger-request-validator-core" 

Custom framework gives more flexibility and more control over tests and removes dependency to specific 3rd party tools/solutions.

## 3. "A few sample tests (without any programming) using your preferred tools."

In the test suite there would be several test classes corresponding to functionality domains to be tested.
API request contest would be saved as JSON files with placeholders to adjust for usage.  
Tests themselves would make appropriate API call, receive response and after the loading of the API specification - will verify against it.
By using mentioned library we would get very detailed report on what was wrong in the response if such case would arise.  
Test launch would be just a singe command in command line making them easy to launch in both local environment as well as CI/CD tool (e.g. Jenkins, Bamboo etc.)