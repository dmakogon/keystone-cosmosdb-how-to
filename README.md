# keystone-cosmosdb-how-to
How to run keystone.js with Azure Cosmos DB + MongoDB API
---
title: 'Azure Cosmos DB: Deploy Keystone.js with the MongoDB API | Microsoft Docs'
description: Presents how to configure Keystone.js to use the Azure Cosmos DB MongoDB API, and deploy to Azure Web Apps.
services: cosmos-db, azure-web-apps
documentationcenter: ''
author: davimak
manager: sarasp
editor: ''

ms.assetid: 
ms.service: cosmos-db
ms.custom: quick start connect
ms.workload: 
ms.tgt_pltfrm: na
ms.devlang: dotnet
ms.topic: hero-article
ms.date: 08/08/2017
ms.author: davimak

---
# Azure Cosmos DB: Deploy Keystone.js with Cosmos DB and the MongoDB API

Azure Cosmos DB is Microsoft’s globally distributed multi-model database service. You can quickly create and query document, key/value, and graph databases, all of which benefit from the global distribution and horizontal scale capabilities at the core of Azure Cosmos DB. 

This quick start demonstrates how to build and run a Keystone.js CMS locally, using the Cosmos DB emulator. You'll then create an Azure Cosmos DB account, document database, and collection using the Azure portal, and configure Keystone.js to use your new database. Finally, you'll deploy your new Keystone.js CMS to an Azure Web App.

## Prerequisites

- Node.js + npm

Keystone.js requires Node.js, as well as npm. You'll need to make sure these are installed.

- Git

This quickstart uses git integration when publishing to Azure. If you'll only be testing locally, you won't need git.

- Download the [Azure Cosmos DB Emulator](https://docs.microsoft.com/en-us/azure/cosmos-db/local-emulator). The emulator is currently only supported on Windows. This quickstart will also show how to use Keystone.js with a production Cosmos DB database in Azure, which can be done from Windows, Mac, or Linux.

- If you don’t already have Visual Studio Code installed, you can install [VS Code](https://code.visualstudio.com/Download) for your platform (Windows, Mac, Linux).

<a id="create-keystone"></a>
## Create a Keystone.js instance

TODO:

 - Install generator-keystone
 - Install Yeoman
 - Generate CMS
 - Modify gallery (fix sort bug)
 - Point MongoDB connection to Cosmos DB emulator
 
 ### generator-keystone

 When creating a Keystone.js CMS, you get to choose which components will be included (blog, gallery, contact form), what templating style to use (Handlebars, etc.), and a photo-hosting account. A separate project, `generator-keystone`, contains the instructions for creating your customized Keystone CMS.

 To install `generator-keystone`, execute the following `npm` command:

```
npm install -g generator-keystone
```

### yeoman

`Yeoman` is the tool which executes the instructions found in `generator-keystone`. To install `yeoman`, execute the following `npm` command:

```
 npm install -g yo
 ```

### Generate your Keystone.js CMS

Now comes the fun part: creating your CMS. Navigate to a directory where you'd like to place your Keystone.js deployment, and run the following `yeoman` command:

```
yo keystone
```
This will walk you through a few questions about which components you'd like to install, and which template style you'd prefer. You'll also be able to specify an admin username.

For this example, the blog and gallery will be created, using Handlebars and the default photo-hosting settings:

```
TODO: capture prompts+responses
```

As soon as all questions are answered, `yeoman`, using the instructions from `generator-keystone`, creates your new Keystone.js CMS.

## Fixing the gallery

If you choose to include a gallery, you'll need to fix a small bug related to gallery sorting. Keystone specifies an incorrect property to sort the gallery by.

With VS Code (or any other editor), open **TODO: FILENAME** and change the following:

```
TODO: code fix for sort order
```

### Pointing Keystone.js to Cosmos DB emulator

The Cosmos DB emulator listens on port 10250 and 10255, and has a fixed username and password. The connection string looks like this:

```
TODO: Connection string
```

In the **TODO: CONFIG FILE** file, add the connection string:

```
TODO: MONGODB connection string in config file
```
 
 ### Test Keystone.js locally

 Navigate into your newly-created Keystone.js directory, and execute the following command:

 ```
 node keystone
 ```

 At this point, you should be able to browse to `https://localhost:3000` and navigate your new Keystone.js CMS.

 ## Deploy your CMS to Azure
 
 To deploy your new Keystone CMS to Azure, you'll create an Azure Web App, along with git integration.

 <a id="create-account"></a>
### Create a database account

TODO

### Create an Azure Web App with Git integration

### Configure git within your local Keystone folder

From the Azure portal, navigate to **TODO: Configuration tab**, and copy the git path. Then, run the following command from your keystone.js cms directory:

```
TODO: ADD GIT REMOTE
```
### Create Cosmos DB database with MongoDB API

### Configure keystone to use Cosmos DB databse in Azure
From the portal, copy your database connection string, username, and password into three configuration properties in your Web App:

**TODO: Screenshot of portal with app settings**

Remove the connection string from the keystone configuration file:

**TODO: Screenshot of removed configuration settings**

### Deploy code to Azure

Now that your local folder is configured correctly, add the Keystone content:

```
git add .
git commit -m "Add keystone.js cms"
git push
```

At this point, your keystone.js cms code will be pushed to your Web App. You can monitor its status on the **TODO: Page name** tab:

**TODO: screenshot of deployment in progress**

When the deployment is complete, open a browser to view your web app, at `https://<yourwebapp>.azurewebsites.net`. You should see the keystone welcome page:

**TODO: screenshot of keystone running in Azure**

Login, and create a simple blog post. Then, navigate to the Cosmos DB databsae you set up earlier, and navigate to the query explorer. Here, you can query your blog collection and find your new blog post:

**TODO: screenshot of blog post in query explorer**

## Clean up resources

If you're not going to continue to use this app, delete all resources created by this quickstart in the Azure portal with the following steps:

 1. From the left-hand menu in the Azure portal, click **Resource groups** and then click the name of the resource group you created. 
 2. On your resource group page, click **Delete**, type the name of the resource to delete in the text box, and then click **Delete**.



