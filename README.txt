#ABOUT WINCAST

## Overview
WinCast is an application for visualizing the historical forecasts of the weather conditions in Winnipeg, Manitoba.

The application is split into three main parts:
1. A FrontEnd: an Angular web application that queries the rest API backend server by date and displays the data that returns from the server call
2. A BackEnd: an Express server which connects to a PostgreSQL database server and services the client-side requests.
3. A PostgreSql database: a local PostgreSQl instance that stores the weather forecasts.

## Source Code

The source code of the application is available at https://github.com/Emmanuel289/WinCast.git


## Dependencies

- [Node.js](https://nodejs.org/en): The Node.js distribution comes prepackaged with a Node Package Manager (NPM) client which is used to install required modules and    dependencies for the application.

- [Express](https://www.npmjs.com/package/express): Express is a lightweight Node.js web application framework for building web and mobile applications.

- [Sequelize](https://sequelize.org/) is an ORM for SQL databases.

- [Dotenv](https://www.npmjs.com/package/dotenv): Dotenv is a module that loads environment variables from a .env file into a local or cloud environment.

- [Multer](https://www.npmjs.com/search?q=multer): Middleware for handling forms and tables.

- [Nodemon](https://www.npmjs.com/package/nodemon): Nodemon is a tool that automatically restarts a Node.js application when file changes are detected.

## Installation

- Clone the source code for the application at https://github.com/Emmanuel289/WinCast.git.

- Navigate to the ```backend/ ``` folder within the folder tree and execute ``` npm install && npm start ``` to install the dependencies for the backend and start the backend service.

- Navigate to the ``` frontend/``` folder and execute ``` npm install && ng serve --open ``` to install the dependencies for the web application and start the frontend service.

- Start a postgres client using the ```psql ``` startup shell and connect to the database (Optional). 


### Querying the Weather Database for Forecasts
 - The `weekly_forecast.js` located inside the `backend/models/` folder contains the schema for defining and composing a weekly forecast into a table for storage in the database. 
 - The 'routes.rest' file contains a list of standard HTTP methods for querying the local server which forwards the requests to the database. For example, the following request adds a new record to the data set
 
 ``` POST http://localhost:8000/api/v0/forecasts 
Content-Type: application/json

{
    "date_time_local": 2024,

    "temperatures": "High 25"

}
```

 - [Postman] (https://www.postman.com/downloads/) can be used to upload a csv file of new datasets which creates new records or updates existing records in the database.


### Design Considerations and Future Iterations:

- An SQL engine was the choice of the database service because the weather forecasts are contained in tables and we might want to persist their storage.
- The UI of the application is a skeleton in its present form and does not do much. It will be updated with presentation logic in the future.
 