# MongoDB Realm Sync Backend

This app has been deplpoyed to WooliesX -> Sandbox -> sanbox-0 cluster. Follow below steps to deploy it to your cluster.

## 1. Install `mongodb-realm-cli`

You can import the ready-made MongoDB Realm backend using the
`mongodb-realm-cli`, which you can install with npm:

```bash
npm install -g mongodb-realm-cli
```

## 2. Create an Atlas cluster with MongoDB 4.4+

To have a backend for your Task Tracker app, you will need a MongoDB Atlas
cluster with MongoDB 4.4 or higher. To create an Atlas account, project, and cluster, visit the [Atlas
UI](https://cloud.mongodb.com/?tck=docs_realm).

> ⚠️ Sync requires MongoDB 4.4 or above. Be sure to select at least MongoDB
> version 4.4 when building your cluster!

## 3. Create an API Key and authenticate the CLI

To authenticate with the `realm-cli`, you must create an API key with **Project
Owner** permissions for your project in the **Project Access Manager** view.
Click the **Access Manager** at the top of the Atlas view to find it. Please
follow the [instructions on the MongoDB documentation
site](https://docs.mongodb.com/realm/deploy/realm-cli-reference/#authenticate-a-cli-user)
for more information.

Once created, pass the API keys to `realm-cli login` to log in:

```bash
realm-cli login --api-key=[public API key] --private-api-key=[private API key]
```

## 4. Update clusterName in config
Modify /services/mongodb-atlas/config.json to point to your cluster.

## 5. Import the Realm backend app

If logged in successfully, you can now import the app:

```bash
cd realm-tutorial-backend
realm-cli import
```

Follow the prompts and wait for the app to deploy.