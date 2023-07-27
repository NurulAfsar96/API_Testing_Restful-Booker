
# API_Testing_Restful-Booker



## Tools used
- Postman
- Newman
## Prerequisite

- Jdk
- Node Js
- Newman
- Html Report Library
## Testing Site

```
https://restful-booker.herokuapp.com/apidoc/index.html#api-Ping-Ping
```
## Collection
### PracticeProject

In this project, all of my HTTP requests are grouped into a Collection named **PracticeProject**. I sent several requests to retrieve data from the source. Here is my HTTP Request list.

- Create Token
- Get All Booking IDs
- Get Booking info based upon ID
- Create New Booking
- Create New Booking with Dynamic variables
- Get new bookings with parameterized ID
- Update Booking
- Partial Update Booking
- Delete Booking


## API Requests

### **Create Token**
**HTTP Request**
```
POST
```
**Request URL**
```http
  https://restful-booker.herokuapp.com/auth
```
**Body**

```
{
"username" : "admin",
"password" : "password123"
}
```

**Response**

```
{
    "token": "8a1bd58c78e379f"
}
```
**Status**

```
200 OK
```
###
### **Get All Booking IDs**
**HTTP Request**
```
GET
```
**Request URL**
```http
  https://restful-booker.herokuapp.com/booking
```
**Body**

```
N/A
```

**Response**

```
[
    {
        "bookingid": 662
    },
    {
        "bookingid": 475
    },
    {
        "bookingid": 188
    },
    {
        "bookingid": 590
    }
]
```
**Status**

```
200 OK
```
###
### **Get Booking info based upon ID**
**HTTP Request**
```
GET
```
**Request URL**
```http
  https://restful-booker.herokuapp.com/booking/1
```
**Body**

```
N/A
```

**Response**

```
{
    "firstname": "Mary",
    "lastname": "Ericsson",
    "totalprice": 636,
    "depositpaid": true,
    "bookingdates": {
        "checkin": "2022-01-24",
        "checkout": "2023-02-26" 
        }
}
```
**Status**

```
200 OK
```
###     
### **Create New Booking**
**HTTP Request**
```
POST
```
**Request URL**
```http
  https://restful-booker.herokuapp.com/booking
```
**Body**

```
{
    "firstname" : "Nurul",
    "lastname" : "Afsar",
    "totalprice" : 1680,
    "depositpaid" : true,
    "bookingdates" : {
        "checkin" : "2023-01-07",
        "checkout" : "2019-01-12"
    },
    "additionalneeds" : "Breakfast"
}
```

**Response**

```
{
    "bookingid": 1534,
    "booking": {
        "firstname": "Nurul",
        "lastname": "Afsar",
        "totalprice": 1680,
        "depositpaid": true,
        "bookingdates": {
            "checkin": "2023-01-07",
            "checkout": "2019-01-12"
        },
        "additionalneeds": "Breakfast"
    }
}
```
**Status**

```
200 OK
```
###
### **Create New Booking with Dynamic variables**
**HTTP Request**
```
POST
```
**Request URL**
```http
  https://restful-booker.herokuapp.com/booking
```
**Body**

```
{
    "firstname" :"{{FirstName}}",
    "lastname" :"{{LastName}}",
    "totalprice" :"{{TotalPrice}}",
    "depositpaid" :"{{DepositPaid}}",
    "bookingdates" : {
        "checkin" : "{{CheckIn}}",
        "checkout" : "{{CheckOut}}"
    },
    "additionalneeds" : "{{AdditionalNeeds}}"
}
```

**Response**

```
{
    "bookingid": 3799,
    "booking": {
        "firstname": "Cassandra",
        "lastname": "Lubowitz",
        "totalprice": 11581,
        "depositpaid": true,
        "bookingdates": {
            "checkin": "2023-07-27",
            "checkout": "2023-10-25"
        },
        "additionalneeds": "Snacks"
    }
}
```
**Status**

```
200 OK
```
###
### **Get new bookings with parameterized ID**
**HTTP Request**
```
GET
```
**Request URL**
```http
  https://restful-booker.herokuapp.com/booking/
```
**Body**

```
N/A
```

**Response**

```
{
    "firstname": "Margarita",
    "lastname": "Conroy",
    "totalprice": 14115,
    "depositpaid": true,
    "bookingdates": {
        "checkin": "2023-07-27",
        "checkout": "2023-08-14"
    },
    "additionalneeds": "Dinner"
}
```
**Status**

```
200 OK
```
##
### **Update Booking**
**HTTP Request**
```
PUT
```
**Request URL**
```http
  https://restful-booker.herokuapp.com/booking/
```
**Request Header**

```
Cookie:     token= "8a1bd58c78e379f"
```
**Body**

```
{
    "firstname": "Friday",
    "lastname": "Lann",
    "totalprice": 99761,
    "depositpaid": true,
    "bookingdates": {
        "checkin": "2024-08-15",
        "checkout": "2024-09-05"
    },
    "additionalneeds": "Breakfast"
}
```

**Response**

```
{
    "firstname": "Friday",
    "lastname": "Lann",
    "totalprice": 99761,
    "depositpaid": true,
    "bookingdates": {
        "checkin": "2024-08-15",
        "checkout": "2024-09-05"
    },
    "additionalneeds": "Breakfast"
}
```
**Status**

```
200 OK
```
###
### **Partial Update Booking**
**HTTP Request**
```
PATCH
```
**Request URL**
```http
  https://restful-booker.herokuapp.com/booking/
```
**Request Header**

```
Cookie:     token= "8a1bd58c78e379f"
```
**Body**

```
{
    "firstname": "Nurul Afsar",
    "lastname": "Johnny"
}
```

**Response**

```
{
    "firstname": "Nurul Afsar",
    "lastname": "Johnny",
    "totalprice": 99761,
    "depositpaid": true,
    "bookingdates": {
        "checkin": "2024-08-15",
        "checkout": "2024-09-05"
    },
    "additionalneeds": "Breakfast"
}
```
**Status**

```
200 OK
```
###
### **Delete Booking**
**HTTP Request**
```
DELETE
```
**Request URL**
```http
  https://restful-booker.herokuapp.com/booking/
```
**Request Header**

```
Cookie:     token= "8a1bd58c78e379f"
```
**Body**

```
N/A
```

**Response**

```
Created
```
**Status**

```
201 Created
```
###
## Environment Variables

To run the collection in Postman, I use a set of Environment Variables. I can change the values of the variables to pass the data between requests and tests.

`baseURL` ,`Token`,`BookingID` ,`FirstName`,`LastName` ,`TotalPrice`,`DepositPaid` ,`CheckIn`,`CheckOut` ,`AdditionalNeeds`


## Newman and Library Install Process
- Newman install command line

```bash
  npm install -g newman
```
- Newman Library install command line

```bash
  npm install -g newman-reporter-htmlextra
```
## Report Generate Process
To generate the report in HTML,

```bash
  newman run PracticeProject.postman_collection.json -e PracticeProject_Env.postman_environment.json -r cli,htmlextra
```
## Newman Report Summary
![Newman_summary](https://github.com/NurulAfsar96/API_Testing_Restful-Booker/assets/90999889/b1f14150-437c-4cfa-bd09-72d9d548cd15)


![Newman_TotalRequest](https://github.com/NurulAfsar96/API_Testing_Restful-Booker/assets/90999889/79f4cd11-25fe-476b-8889-66537185fc28)


