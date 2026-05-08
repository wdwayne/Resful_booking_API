# API Test Strategy – Restful Booker

## Project Overview
This project focuses on automated API testing of the Restful Booker application using Postman and Newman.
The goal of the project is to validate core booking functionality, authentication, CRUD operations, and negative scenarios while demonstrating API automation and test organization practices.

---

# Scope
The following endpoints were tested:
- POST /auth
- GET /booking
- GET /booking/{id}
- POST /booking
- PUT /booking/{id}
- PATCH /booking/{id}
- DELETE /booking/{id}

---

# Testing Objectives
The objective of this testing effort was to verify:
- Authentication functionality
- Booking creation and retrieval
- Full and partial booking updates
- Booking deletion
- Error handling for invalid requests
- API response structure and status codes
- Basic response performance

---

# Testing Types Performed

## Functional Testing
Validated that endpoints returned expected responses and performed intended actions.

Examples:
- Creating bookings
- Updating booking information
- Retrieving booking details

---

## Negative Testing
Validated how the API handled invalid or unexpected scenarios.
Examples:
- Updating non-existent booking IDs
- Deleting already deleted bookings
- Invalid authentication scenarios

---

## Response Validation
Validated:
- Status codes
- Response body structure
- Expected response fields
- Data correctness
Examples:
- Token returned after authentication
- Booking ID returned after booking creation
- Updated values reflected in responses

---

## Performance Validation
Basic response time validation was performed to ensure API responses completed within acceptable limits.
Example:
- Response time under 500ms

---

# Authentication Strategy
Authentication was handled using the `/auth` endpoint.
A valid token was:
1. Generated before protected requests
2. Stored as a Postman environment variable
3. Reused in authenticated requests through request headers
Example: Cookie: token={{token}}

# Test Data Management

Dynamic test data was managed using Postman environment variables.
Variables used:
- token
- bookingId
The bookingId variable was dynamically captured after booking creation and reused in update, retrieval, and delete requests.

# Request Chaining
Request chaining was implemented to support automated CRUD workflows.
Flow:
1. Authenticate user
2. Create booking
3. Store booking ID
4. Retrieve booking
5. Update booking
6. Delete booking
7. Validate invalid delete scenario
This approach improved test reliability and reduced manual intervention.

# Automation Strategy
Automation was implemented using:
- Postman test scripts
- JavaScript assertions
- Newman CLI execution
Assertions validated:
- Status codes
- Response structures
- Response values
- Performance expectations

# Risks and Limitations
- The API uses shared public test data which may occasionally produce inconsistent results.
- Generated booking IDs may become invalid if deleted during testing.
- Rate limiting and uptime of the public API are outside tester control.

# Tools Used
- Postman
- Newman
- JavaScript
- GitHub
- GitHub Actions

# Conclusion
This project demonstrates:
- API functional testing
- Automated API validation
- Authentication handling
- Request chaining
- Positive and negative test coverage
- Basic automation workflow integration