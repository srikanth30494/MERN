# UMG Swift Consumption Tool Client (sst-app-client)

## About:
The Swift consumption tool was designed with Modern data and development technologies by Data & Analytics team @UMG.

## Requirements:
Make sure your nodeJS version is >= 4.2.1 and npm version is >=3.0.0.

## Configs
sst-app-client can be build locally for both Development and Production Environments.
All the environment variables are set in Webpack to build it in both local and production environments.

## Setting up project locally:
In order to `Run` the project locally in development mode, you need access to two repositories.
1. sst-app-client (Client)
2. sst-app-api (API)

### For sst-app-api

In order to run the repo locally do the following:

	$ git clone git@github.com:umg/sst-app-api.git

	$ $npm install

	$ npm run dev:gql

Once the API is running, you can turn off local authorization by going to the following file location and setting auth : { disabled : true }. When you push this code to dev, qa or prod though don't forget to switch back to false.

	src > config > env > dev.js

Once the API was build, It starts to listen on port 5777. 

For local the Graphql API end point is http://localhost:5777/graphql

### For sst-app-client

Just clone this repo or download the zip file.
```
$ git clone git@github.com:umg/sst-app-client.git
```
cd into the directory and run
```
$ npm install
```
To start the client
```
$npm start
```
 Navigate to the following URL to verify that your application is running.
 
 http://localhost:3000
 

