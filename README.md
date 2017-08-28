# UMG Swift Consumption Tool Client (sst-app-client)

## About:
The Swift consumption tool was designed with Modern data and development technologies by Data & Analytics team @UMG.

## Requirements:
Make sure your nodeJS version is >= 4.2.1 and npm version is >=3.0.0.

## Configs:
All the environment variables and configs are set in Webpack to build the App in both local and production environments.
For Development version uses `webpack.common.dev.js & webpack.dev.js` and for production version `webpack.common.aot.js & webpack.prod.js` from the config folder.

## Setting up project locally:
In order to `Run` the project locally in development mode, you need access to two repositories.
1. sst-app-api (API)
2. sst-app-client (Client)

### For sst-app-api:

In order to run the repo locally do the following:

	$ git clone git@github.com:umg/sst-app-api.git

	$ $npm install

	$ npm run dev:gql

Once the API is running, you can turn off local authorization by going to the following file location and setting auth : { disabled : true }. When you push this code to dev, qa or prod though don't forget to switch back to false.

	src > config > env > dev.js

Once the API was build, It starts to listen on port 5777. 

For local the Graphql API end point is http://localhost:5777/graphql

### For sst-app-client:

Just clone this repo or download the zip file.
```
$ git clone git@github.com:umg/sst-app-client.git
```
cd into the directory and run
```
$ npm install
$ npm start
```
 Once everything was setup correctly 
 Navigate to the following URL to verify that your application is running.
 
 http://localhost:3000
 
**Note: To be able to run project locally, you need to have valid UMG Global credentials**

## Production Environment:

This project uses Angular AOT Compilation for the production purpose where as in development it uses JIT Compilation.
AOT Compilation was set up using the package [ngc-webpack](https://github.com/shlomiassaf/ngc-webpack).

Use the following command to build the Application for production environment

```
npm run build:prod
```
Once the App was build successfully, you should be able to find `dist` folder with the necessary production files.

To run the production files locally, make sure you install [http-server](https://github.com/indexzero/http-server) globally or any other you prefer similar to [http-server](https://github.com/indexzero/http-server)

cd into the `dist` folder and run the following command
```
http-server -p 8080 -g -o
```
where `-p 8080` is the port http-server runs on, `-g` serves the `.gzip` files from the dist folder instead of `.min.js` files and `-o` Opens browser window after starting the server.

## Docker Build:

Docker uses the command `npm run build` while building the images in the containers.

If you are building a development version, the `build` command in `Package.json` should be set to `npm run build:dev` and for the production version it should be set to `npm run build:prod`.

Please make these changes to `Package.json` accordingly until they are set in the Docker file.

## Tech Stack
Primarily built on **Angular2**  
CSS Pre processors: Sass  
CSS Frame work: Bootstrap  
API: Graphql with [Apollo-client](http://dev.apollodata.com/angular2/) for Angular.  


## Running Lint:
Use the following command to run lint check before you PR. It's must that you perform lint check to avoid errors during the PR process.
```
npm run lint
```
## Bugs and Issues:
Project team uses `Github project` feature to track the issues and bugs, you can find them at the below URL.  
https://github.com/orgs/umg/projects/3

## Application URL's
**For Development:**   
https://swift-dev.umusic.com/  
**For QA:(Prod)**   
https://swift-qa.umusic.com/
