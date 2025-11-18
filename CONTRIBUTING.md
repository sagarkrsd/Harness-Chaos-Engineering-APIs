# Contributing to Harness Chaos Engineering API Documentation

Thank you for your interest in contributing! Here's how you can help:

## Getting Started

1. Fork the repository
2. Create your feature branch: `git checkout -b feature/amazing-feature`
3. Commit your changes: `git commit -m 'Add some amazing feature'`
4. Push to the branch: `git push origin feature/amazing-feature`
5. Open a Pull Request

## Development Setup

### Prerequisites

- Node.js 16+
- Postman 9.0.0+
- Git

### Setup Steps

#### 1. Import the Collection

##### Using Postman Desktop (Recommended)

1. Open Postman
2. Click "Import" > "File"
3. Select the collection file from `postman/collections/`
4. Click "Import"

##### Using Postman Web

1. Visit [Harness Chaos Engineering Public Workspace](https://www.postman.com/harness-chaos-engineering/harness-chaos-engineering-public/overview).
2. Click on the postman collection you want to use such as [Harness Chaos Engineering APIs - REST](https://www.postman.com/harness-chaos-engineering/harness-chaos-engineering-public/collection/lwhho9j/harness-chaos-engineering-apis-rest).
3. Click "Fork" to add to your workspace.
4. Select your personal workspace and confirm.

#### 2. Import the Environment

Import the appropriate environment file from `postman/environments/` directory:

- `Prod1.postman_environment.json` for production

##### Using Postman Desktop (Recommended)

1. Open Postman
2. Click "Import" > "File"
3. Select the environment file from `postman/environments/`
4. Click "Import"

##### Using Postman Web

1. Visit [Harness Chaos Engineering Public Workspace](https://www.postman.com/harness-chaos-engineering/harness-chaos-engineering-public/overview).
2. Click on the postman environment you want to use such as [Prod1](https://www.postman.com/harness-chaos-engineering/harness-chaos-engineering-public/environment/25469526-8c7108fd-9f36-4d0f-83f4-80c63e4ba474).
3. Click "Fork" to add to your workspace.
4. Select your personal workspace and confirm.

#### 3. Update Environment Variables

Update environment variables:

| Variable Name        | Description                     |
| -------------------- | ------------------------------- |
| `base_url`           | The base URL for the API        |
| `url`                | The URL for the API             |
| `account_id`         | Your Harness account ID         |
| `org_id`             | Your Harness organization ID    |
| `project_id`         | Your Harness project ID         |
| `env_id`             | Your Harness environment ID     |
| `delegate_selectors` | Your Harness delegate selectors |
| `API-KEY-TOKEN`      | Your API key token              |

Let's break down the variables:

- `base_url` & `url`

  **NOTE: If you are using chaos postman collection provided by Harness, this value will be pre-filled under postman variables section:**
  - `base_url` -> <https://app.harness.io>
  - `url` -> {{base_url}}/gateway/chaos/manager/api/query

  This is the Harness Chaos Engineering server URL serving the Chaos API requests.

  | Environment | API Type | API Server URL                                           | Description                                                 |
  | ----------- | -------- | -------------------------------------------------------- | ----------------------------------------------------------- |
  | Prod        | REST     | <https://app.harness.io/gateway/chaos/manager/api>       | The base URL for the Harness Chaos Engineering REST APIs    |
  | Prod        | GRAPHQL  | <https://app.harness.io/gateway/chaos/manager/api/query> | The base URL for the Harness Chaos Engineering GraphQL APIs |

- `project_id`

  This is your Harness project ID. Please use the project where you would like to run Chaos experiments.

  You can retrieve your project ID by following the below steps:
  - Go to `Projects` in [Harness](https://app.harness.io/).
  - Select the project where you would like to run the Chaos experiments or create a new project.
  - Click on `Overview`.
  - Copy the value of `Id`.

  **NOTE:** Please make sure to copy the value of `Organization` as well, this will be the value of next required variable `org_id`.

- `org_id`

  This is your Harness organization ID. Please use the organization where you would like to run Chaos experiments.

  You can retrieve your organization ID by following the below steps:
  - See above step to retrieve project_id - you would have copied the value of org_id as well in that step, if not please follow the same steps again to retrieve organization ID.

- `API-KEY-TOKEN`

  You can use an existing Harness API key token of the same Harness account selected in above steps or you can create a new one by following the below steps:
  - Click on MY PROFILE in [Harness](https://app.harness.io/).
  - Go to My API Keys section and click on `+ API Key` button to create a new API Key.
  - Enter a Name for the API Key (optional Description/Tags) and click on Save.
  - Under the newly created API Key, click on `+ Token` button to generate a new token for this API Key.
  - Enter the Name and select the Expiration(time for which this token will be valid) and click on Generate Token.
  - Please make sure to copy the value of the token generated and store somewhere safe, you may not be able to copy this later.

An updated environment file could look like this screenshot:
![Sample Environment](postman/assets/screenshots/environments/hce-prod-env.png)

#### 4. Make changes to the collection and test them

1. Open the [Harness Chaos Engineering APIs - REST](https://www.postman.com/harness-chaos-engineering/harness-chaos-engineering-public/collection/lwhho9j/harness-chaos-engineering-apis-rest) in Postman.
2. Select the environment you want to use (e.g., QA or Prod).
3. Select the request you want to run (e.g., [GET /rest/v2/experiment](https://www.postman.com/harness-chaos-engineering/harness-chaos-engineering-public/request/gcj0m71/get-list-of-chaos-v2-experiments?ctx=code)).
4. Update the `required variables, headers, body, etc.` for the request if any.
5. Click `Send` to run the request.
6. You should see the response in the response tab.

#### 5.Export the updated collection

1. Open the [Harness Chaos Engineering APIs - REST](https://www.postman.com/harness-chaos-engineering/harness-chaos-engineering-public/collection/lwhho9j/harness-chaos-engineering-apis-rest) in Postman.
2. Click on the three dots beside the collection name and select `Export` to export the updated collection.
3. Save the collection to a file in the `postman/collections/` directory.

#### 6. Commit the changes to the repository

1. Review the changes in the collection file.
2. Make sure that the changes are only related to the specific request you have updated and not the entire collection.
3. Commit the changes to the repository.
4. Push the changes to the remote repository.
5. Open a Pull Request.
6. Wait for the PR to be merged.
