# REST-API-with-JSON
For Testing the program
================================
2. Open a browser and go to the url http://ec2-XXXX.amazonaws.com/swagger 
3. You will see a link Employee. Click on the link - Employee
4. All the four REST operations will be displayed - GET, POST, PUT & DELETE.

The Response headers for all the opeartions holds if the opeartion was successful(e.g. 200 OK) and 
also a status message (E.g. Employee Added Successfully etc).

***************************************************************************************************************
1.GET
***************************************************************************************************************
Click on Get & Click on Try it out Button
All the records in the Employee Table will be displayed.


***************************************************************************************************************
2.POST:
***************************************************************************************************************
Click on POST and in the employee parameter field- Give the following json object as the input parameter 
and click on try it out.
{
  "Id": 6,
  "firstName": "test6",
  "lastName": "test6",
  "phoneNumber": "test6",
  "emailId": "test6@gmail.com",
  "age": 6
}

To see if the data is actually updated, click on GET operation again and the newly added 
record will be displayed.


***************************************************************************************************************
3. PUT:
***************************************************************************************************************
Click on PUT and update the phone Number say for the newly added record from test6 to 123456.
give the following input parameters - id: 6 & phoneNumber: 123456 and click try it out.
The phonenumber for the id 6 will be updated from test6 to 123456

To see if its updated,  click on GET operation again and the newly updated record will be displayed.


***************************************************************************************************************
4. DELETE:
***************************************************************************************************************
Click on the DELETE and delte the newly added record 6 and click on try it out.
It should get deleted.

To see if its deleted, click on GET operation again and the record with id 6 should be deleted.

***************************************************************************************************************


Running the curl commands from gitbash:
======================================= 
Open Gitbash and run the following commands for each of the operations

1. GET:
curl -i -X GET --header 'Accept: application/json' 'http://ec2-XXXX.amazonaws.com/employeedetails'

2. POST: Give an ID which is currently not in the employee table, Since Id is the Primary Key
curl -i -X POST -H 'Content-Type: application/json' -H 'Accept: application/json' 'http://ec2-XXXX.amazonaws.com/employee' -d '{"Id": 6, "firstName": "test6", "lastName": "test6", "phoneNumber": "test6", "emailId": "test6@gmail.com", "age": 6}'

3. PUT: 
curl -i -X PUT -H 'Accept: application/json' 'http://ec2-XXXX.amazonaws.com/employee/6/123456' -d '{"Id": 6, "phoneNumber": "123456"}'

4. DELETE: 
curl -i -X DELETE --header 'Accept: application/json' 'http://ec2-XXXX.amazonaws.com/employee/delete/6'
