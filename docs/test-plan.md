# Test Plan Overview
This test plan outlines the testing approach used for the Restful Booker API. The Restful Booker is a free use API for practicing testing it comes with CRUD and authentication features.

# Objectives
1. Verify that core functionallities work as expected
2. Identify and document defects found within the application
3. Observe system behaviour under valid and invalid conditions


# Test Scope
*In scope*
- Authentication
- CRUD functionalities
- Performance testing

*Out of Scope*
- Third party integration
- Backend/Database verification

# Test Stratagy 
testing was conducted using the following approaches
1. Exploritory testing 
2. Negative testing
3. API testing
4. Automation testing
5. Functional testing
6. Response Validation

# Test Deliverables
- Test cases
- HTML report
- Screenshots

# Risks and Mitigation
Risk: Unauthorised access to protected endpoints
Mitigation: Verify that users are not allowed access to protected endpoints with proper authentication.

Risk: Enpoints unable to handle large traffic
Mitigation: Run performance tests to ensure enpoints are able to handle large traffic

Risk: Submitting booking requests with incomplete data/information.
Mitigation: Perform validations tests to 


## Entry and Exit criteria

### Entry Criteria
- Application is accessible
- Valid login credentials

### Exit Criteria
- All End points Tested