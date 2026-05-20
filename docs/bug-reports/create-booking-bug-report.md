### RB-BUG_001 - POST /API accepts submissions with incomplete JSON field/s

**Environment**
- API Version: v1.0.0
- Method: POST
- Endpoint: /booking
- Tool: Postman/newman

**Description**
When incomplete JSON data is submitted i.e empty firstname or lastname field the API still accepts the request and creates a booking with a 200 status code.

**Preconditions**
- User has access to the create booking endpoint 
- user has been authenticated

**Steps To Recreate**
1. Send a POST request to /booking
2. set firstname field to an empty string 
3. Send request 

**Request Payload**
{
  "firstname": "",
  "lastname": "Smith",
  "totalprice": 123,
  "depositpaid": true,
  "bookingdates": {
    "checkin": "2025-01-01",
    "checkout": "2025-01-02"
  }
}

**Expected Results**
- API should should reject request with a 400 bad request status code
- An appropriate validation message should be returned indicating the firstname field is required

**Actual Results**
- API returns a 200 status code and creates a booking

**Response**
{
    "bookingid": 2200,
    "booking": {
        "firstname": "",
        "lastname": "Cliffington",
        "totalprice": 123,
        "depositpaid": true,
        "bookingdates": {
            "checkin": "2018-01-01",
            "checkout": "2019-01-01"
        },
        "additionalneeds": "Breakfast"
    } 
}

**Severity**
Hight

**Priority**
High

**Notes**
- A booking can be created without a first and/or last name leading to lost bookings, unable to find the customer that booked or users claiming the wrong bookings


### RB-BUT-002 API creates booking with negative totalprice

**Environment**
- API Version: v1.0.0
- Method: POST
- Endpoint: /booking
- Tool: Postman/newman

**Description**
API still creates a booking even when the totalprice field has a negative number.

**Preconditions**
- User has access to the create booking endpoint 
- user has been authenticated

**Steps To Recreate**
1. Fill out all JSON Fields 
2. Add a negative number in the total price field
3. submit request

**Request Payload**
{
    "firstname" : "John",
    "lastname" : "Cliffington",
    "totalprice" : -250,
    "depositpaid" : true,
    "bookingdates" : {
        "checkin" : "2018-01-01",
        "checkout" : "2019-01-01"
    },
    "additionalneeds" : "Breakfast"
}

**Expected Results**
- API rejects request with a 400 bad request status
- API returns an appropriate message indicating price field is invalid

**Actual Results**
- API returns a 200 status code and creates a booking

**Response**
{
    "bookingid": 545,
    "booking": {
        "firstname": "John",
        "lastname": "Cliffington",
        "totalprice": -250,
        "depositpaid": true,
        "bookingdates": {
            "checkin": "2018-01-01",
            "checkout": "2019-01-01"
        },
        "additionalneeds": "Breakfast"
    }
}

**Severity**
Hight

**Priority**
High

**Notes** 
- Bookings can be created with negative founds which could greatly impact the business financially