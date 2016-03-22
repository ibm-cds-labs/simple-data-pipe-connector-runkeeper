# Simple Data Pipe connector for [Runkeeper](https://runkeeper.com/developer/healthgraph/)

This connector uses the [Runkeeper Health Graph API](https://runkeeper.com/developer/healthgraph/) to fetch the following data from your Runkeeper account:

 * Profile
 * Settings
 * Friends
 * Personal Records
 * Strength Training Activities
 * Fitness Activities
 * Background Activities
 * Weight Measurements
 * Sleep Measurements
 * Nutritional Measurements
 * Diabetes Measurements
 * General Measurements
 * Change Log

The [Simple Data Pipe SDK](https://github.com/ibm-cds-labs/simple-data-pipe-sdk) is used to store the data in Cloudant. Depending on the data type one or more JSON records are created and stored in Cloudant. Here are some sample JSON records:

##### Message record structure for Profile:
```json
{
 "..." : "<cloudant document properties such as _id and _rev>",
 "elite": "false",
 "profile": "https://runkeeper.com/user/XXXXXXXXXX",
 "name": "<FirstName LastName>",
 "pt_type": "profile"
}
```

##### Message record structure for a single Fitness Activity:
```json
{
 "..." : "<cloudant document properties such as _id and _rev>",
 "utc_offset": -5,
 "duration": 999.99,
 "start_time": "Tue, 22 Mar 2016 06:34:36",
 "total_calories": 250,
 "tracking_mode": "outdoor",
 "total_distance": 2937.4032807311162,
 "entry_mode": "API",
 "has_path": true,
 "source": "Runkeeper",
 "type": "Running",
 "uri": "/fitnessActivities/XXXXXXXXX",
 "pt_type": "fitness_activities"
}
```

For more information regarding each data type, see the [Runkeeper Health Graph API](https://runkeeper.com/developer/healthgraph/).

Need to load data from other sources? Check out the [connector repository](https://developer.ibm.com/clouddataservices/simple-data-pipe-connectors/).

### Pre-requisites

##### General 
 A valid Runkeeper account is required to use this connector.

##### Deploy the Simple Data Pipe

 [Deploy the Simple Data Pipe in Bluemix](https://github.com/ibm-cds-labs/simple-data-pipe) using the Deploy to Bluemix button or manually.

##### Services

This connector does not require any additional Bluemix service.


##### Install the Simple Data Pipe connector for Runkeeper

  When you [follow these steps to install this connector](https://github.com/ibm-cds-labs/simple-data-pipe/wiki/Installing-a-Simple-Data-Pipe-Connector), add the following line to the dependencies list in the `package.json` file: 

```
"simple-data-pipe-connector-runkeeper": "https://github.com/ibm-cds-labs/simple-data-pipe-connector-runkeeper.git"
```

##### Enable OAuth support and collect connectivity information

 You need to register the Simple Data Pipe application before you can use this connector to load data.
 
 * Open the [Runkeeper Partner Portal](https://runkeeper.com/partner) and log in.

    > If you don’t yet have an account, sign up.
 * In the top menu click **Applications**.
 * Click the **Register a New Application** tab.
 * Enter the following information:
    *   Name of the app. Enter any unique identifier, like My Simple Data Pipe Demo App.
    *   Description of the app.
    *   Organization.
 * Click the **Register Application** button on the bottom.
 * Under your application name click **Keys and URLs**
 * Copy the _Client ID_ and _Client Secret_ values. You’ll need this information to configure your Runkeeper data pipes.


### Using the Simple Data Pipe connector for Runkeeper

To configure and run a pipe

1. Open the Simple Data Pipe web console.
2. Select __Create A New Pipe__.
3. Select __Runkeeper__ for the __Type__ when creating a new pipe.
4. In the _Connect_ page, enter the _Client ID_ and _Client Secret_ from the Keys and URLs page for your Runkeeper application.
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
