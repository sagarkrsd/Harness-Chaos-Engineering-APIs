Harness Chaos Engineering API: Comprehensive User Guide

1. Introduction
   The Harness Chaos Engineering API allows you to programmatically manage chaos experiments, environments, and infrastructure. This guide will help you get started with the Postman collection and integrate it into your workflows.
2. Prerequisites
   Before you begin, ensure you have:
   Postman Desktop App (version 9.0.0 or later)
   Active Harness Chaos Engineering account
   Required permissions in your Harness account
   API key with appropriate permissions

3. Setup Instructions
   3.1 Import the Collection
   Using Postman Web:
   Visit the Harness Chaos Engineering Public Workspace
   Click Fork to add it to your workspace.
   Select your personal workspace and click Fork Collection.

Using Postman Desktop:
Open Postman
Click "Import" > "Link"
Use collection link for import <https://www.postman.com/collections/lwhho9j/harness-chaos-engineering-apis-rest>
Click "Continue" > "Import"

3.2 Set Up Environment
In Postman, click Environments > Create Environment
Name it (e.g., Harness CE Production) and
Click Save.

A Sample Environment

Listed below are some of the required inputs(stored as postman variables) and how to access (or generate) them. We will refer these variables in the API requests listed under this collection.
base_url and url

This is the Harness Chaos Engineering server URL serving the Chaos API requests.
You can find this URL in the Chaos API doc(`top right`).
For instance, <https://app.harness.io/gateway/chaos/manager/api/query> is the Harness CE server URL for production environment. If you are using chaos postman collection provided by Harness, this value will be pre-filled under postman variables section:
base_url -> <https://app.harness.io>
url -> {{base_url}}/gateway/chaos/manager/api/query
account_id

This is your Harness Account ID. Please use the account where you would like to run Chaos experiments.
You can retrieve your account Id by following the below steps:
Go to ACCOUNT SETTINGS in [Harness](https://app.harness.io/).
Click on Overview.
Copy the value of Account ID.

project_id

This is your Harness project Id. Please use the project where you would like to run Chaos experiments.
You can retrieve your project Id by following the below steps:
Go to `Projects` in [Harness](https://app.harness.io/)..
Select the project where you would like to run the Chaos experiments or create a new project.
Click on `Overview`.
Copy the value of `Id`.
Please make sure to copy the value of `Organization` as well, this will be the value of next required variable `org_id`.

org_id

This is your Harness organization Id. Please use the organization where you would like to run Chaos experiments.
You can retrieve your organization Id by following the below steps:
See above step to retrieve project_id - you would have copied the value of org_id as well in that step, if not please follow the same steps again to retrieve organization Id.

API-KEY-TOKEN

You can use an existing Harness API key token of the same Harness account selected in above steps or you can create a new one by following the below steps:
Click on MY PROFILE in [Harness](https://app.harness.io/).
Go to My API Keys section and click on + API Key button to create a new API Key.
Enter a Name for the API Key(optional Description/Tags) and click on Save.
Under the newly created API Key, click on + Token button to generate a new token for this API Key.
Enter the Name and select the Expiration(time for which this token will be valid) and click on Generate Token.
Please make sure to copy the value of the token generated and store somewhere safe, you may not be able to copy this later.

Getting Started With Your 1st Chaos Experiment
Please refer the below postman flow to get started with your 1st chaos experiment <https://flow.pstmn.io/embed/qF94XNW_Jd24f0Xi1f1le/?theme=dark&frame=false>
