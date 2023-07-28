
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

## Documentation
```
https://documenter.getpostman.com/view/24573841/2s9XxsUwFz
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


