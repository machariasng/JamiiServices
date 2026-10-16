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

