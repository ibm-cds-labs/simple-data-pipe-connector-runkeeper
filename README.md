> Hey there! So you want to build your own Simple Data Pipe connector? [Start here](https://github.com/ibm-cds-labs/simple-data-pipe-connector-template/wiki/How-to-build-a-Simple-Data-Pipe-connector-using-this-template).

***


# Simple Data Pipe connector boilerplate for stripe.com

This [Simple Data Pipe](https://developer.ibm.com/clouddataservices/simple-data-pipe/) connector for reddit starter kit has been customized for [stripe.com](http://www.stripe.com) OAuth access. You can build your own special purpose connector by implementing the `getStripeDataSetList` and `fetchRecords` functions in `lib/index.js` to fetch the desired data from stripe.com and optionally enrich it.
### Pre-requisites

##### General 
 A valid stripe user id is required to use this connector.

##### Deploy the Simple Data Pipe

 [Deploy the Simple Data Pipe in Bluemix](https://github.com/ibm-cds-labs/simple-data-pipe) using the Deploy to Bluemix button or manually.

##### Services

This connector does not require any additional Bluemix service.


##### Install the Simple Data Pipe OAuth sample connector 

  When you [follow these steps to install this connector](https://github.com/ibm-cds-labs/simple-data-pipe/wiki/Installing-a-Simple-Data-Pipe-Connector), add the following line to the dependencies list in the `package.json` file: 

> BETA ONLY
```
"simple-data-pipe-connector-oauth-stripe": "https://github.com/ibm-cds-labs/simple-data-pipe-connector-oauth-stripe.git#pp_validation"
```

##### Enable OAuth support and collect connectivity information

 You need to register the Simple Data Pipe application before you can use this connector to load data.
 
 * Open the [stripe.com dashboard](http://www.stripe.com) and log in.

    > If you don’t yet have an account, sign up. You can try these steps with test data. You can create test data through the UI for the Stripe test environment. See their docs for test card numbers and other simulated parameters.


 * On the upper right of the screen, click **Your account** > **Account Settings**.
 * Click the **API Keys** tab.
 * Note the key value for the data you want to copy to Cloudant. You’ll need this string in the next section.
 
    >  To retrieve only test data, copy the value in _Test Secret Key_. To retrieve production data, copy the value in _Live Secret Key_.

 * Click the **Connect** tab.
 * If you never connected to an app before, go to the lower left of the screen and click **Register your platform**. If you have previously connected to an app, click the **Platform Settings** button, then **Register your platform**.
 * In the _standalone accounts_ section enter the following information:
    *   Name of the app. Enter any unique identifier, like My Simple Data Pipe Demo App.
    *   Website URL (used for reference only) of your Simple Data Pipe application. You can get this URL from the Simple Data Pipe browser window you left open. Just copy and paste the URL from the address bar. It is: `https://<your-simple-data-pipe-host-name>.mybluemix.net`.
    *   Redirect URIs. Enter a value for the Stripe environment in which you’re working: development or production. Your entry will be the same for either one: `https://<your--simple-data-pipe-host-name>.mybluemix.net/authCallback`

 * Copy the _client_id_ value for the environment you’re working in: either production or development. You’ll need this string to configure your Stripe data pipes.
 * Click *Done*.


### Using the Simple Data Pipe connector boilerplate for stripe.com

To configure and run a pipe

1. Open the Simple Data Pipe web console.
2. Select __Create A New Pipe__.
3. Select __Stripe OAuth Data Source__ for the __Type__ when creating a new pipe.  
4. In the _Connect_ page, enter the _application id_ and _secret_ from the Stripe account settings page. 
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
