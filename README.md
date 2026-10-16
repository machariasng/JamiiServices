# JamiiServices

The project has three apis cutsomer,account and loans that have been developed using WSO2 MI.

Customer service is a proxy to https://jsonplaceholder.typicode.com/users/{uri.var.customerId}

Account service uses embedded sqlite database to query preexisting account numbers

Loans service simulates loans scoring using http://www.dneonline.com/calculator.asmx soap service


Option 1 

Create .env on the project containing the entry below

accounts_db_url=jdbc:sqlite:D:/Accounts-Family-Bank.db

The sqlite database is provided on the repo. Copy to a suitable location and change the url above

To run the services directly on visul studio using the installed extension click on the build and run button and use testing tool to run some quick tests.


Option 2

To publish the services on APIM and test them you will build on maven and create docker images

Step 1

For the three services developed, use the option of create docker image on visual studio. This does the required build using maven, copies the database file and builds a docker image.
Start the container using below command

docker run -d --name jamiiservices -p 8290:8290 -p 8253:8253 -p 9164:9164 jamiiservices:1.0.0

This will start the container running the services, confirm using below endpoints

http://localhost:8290/apis/accounts/1122334455/balance

http://localhost:8290/apis/customers/1

http://localhost:8290/apis/loans/eligibility

{
  "customerId": "CUST-100245",
  "monthlyIncome": 85000,
  "requestedAmount": 250000,
  "termMonths": 12
}

Step 2

To start a docker container running WSO2 APIM and publish the APIs using the handwritten swagger file



