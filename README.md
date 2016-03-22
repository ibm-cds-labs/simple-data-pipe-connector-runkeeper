> Hey there! So you want to build your own Simple Data Pipe connector? [Start here](https://github.com/ibm-cds-labs/simple-data-pipe-connector-template/wiki/How-to-build-a-Simple-Data-Pipe-connector-using-this-template).

***


# Simple Data Pipe connector for [RunKeeper](https://runkeeper.com/developer/healthgraph/)

This [Simple Data Pipe](https://developer.ibm.com/clouddataservices/simple-data-pipe/) connector for RunKeeper has been customized for [RunKeeper Health Graph](https://runkeeper.com/developer/healthgraph/) OAuth access. You can build your own special purpose connector by implementing the `getRunKeeperDataSetList` and `fetchRecords` functions in `lib/index.js` to fetch the desired data from RunKeeper and optionally enrich it.
### Pre-requisites

##### General 
 A valid RunKeeper account is required to use this connector.

##### Deploy the Simple Data Pipe

 [Deploy the Simple Data Pipe in Bluemix](https://github.com/ibm-cds-labs/simple-data-pipe) using the Deploy to Bluemix button or manually.

##### Services

This connector does not require any additional Bluemix service.


##### Install the Simple Data Pipe connector for RunKeeper

  When you [follow these steps to install this connector](https://github.com/ibm-cds-labs/simple-data-pipe/wiki/Installing-a-Simple-Data-Pipe-Connector), add the following line to the dependencies list in the `package.json` file: 

> BETA ONLY
```
"simple-data-pipe-connector-runkeeper": "https://github.com/ibm-cds-labs/simple-data-pipe-connector-runkeeper.git"
```

##### Enable OAuth support and collect connectivity information

 You need to register the Simple Data Pipe application before you can use this connector to load data.
 
 * Open the [RunKeeper Partner Portal](https://runkeeper.com/partner) and log in.

    > If you don’t yet have an account, sign up.

 * In the top menu, click **Applications**.
 * Click the **Register a New Application** tab.
 * Enter the following information:
    *   Name of the app. Enter any unique identifier, like My Simple Data Pipe Demo App.
    *   Description of the app.
    *   Organization.
 * Click the **Register Application** button on the bottom.
 * Under your application name click **Keys and URLs**
 * Copy the _Client ID_ and _Client Secret_ values. You’ll need this information to configure your RunKeeper data pipes.


### Using the Simple Data Pipe connector for RunKeeper

To configure and run a pipe

1. Open the Simple Data Pipe web console.
2. Select __Create A New Pipe__.
3. Select __RunKeeper__ for the __Type__ when creating a new pipe.
4. In the _Connect_ page, enter the _Client ID_ and _Client Secret_ from the Keys and URLs page for your RunKeeper application.
5. Select the data set (or data sets) to be loaded.
6. Schedule or run the data pipe now.

#### License 

Copyright [2016] IBM Cloud Data Services

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
