---
title : "Preparing"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 1. </b> "
---
Before doing the main content of this workshop, we prepare the services and data for the application.
1. Download the source code of the sam project below

{{%attachments title="SAM source" pattern=".*\.(zip)$"/%}}

2. Run the command below to deploy sam
```
sam build
sam deploy --guided
```

3. Open the console of [CloudFormation]()
4. Wait for the stack to be created, click on the stack **fcj-book-store**

![CreateRepository](/images/1-preparation/1-preparation-1.png?featherlight=false&width=90pc)

5. Press the **Output** tab, write down the API URL

![CreateRepository](/images/1-preparation/1-preparation-2.png?featherlight=false&width=90pc)

6. Load the data file for DynamoDB later

{{%attachments title="SAM source" pattern=".*\.(json)$"/%}}

7. Run the following command at the directory containing the JSON file you just downloaded to write data to the **Books** table in DynamoDB
```
aws dynamodb batch-write-item --request-item file://dynamoDB.json
```

8. Open the console of [AWS DynamoDB]()

![CreateRepository](/images/1-preparation/1-preparation-3.png?featherlight=false&width=90pc)

9. Press **Tables** in the menu on the right

![CreateRepository](/images/1-preparation/1-preparation-4.png?featherlight=false&width=90pc)

10. Click **Explore items**
- Select the table **Books**, the table data has been written on

![CreateRepository](/images/1-preparation/1-preparation-5.png?featherlight=false&width=90pc)

We have prepared the necessary source for the next steps.