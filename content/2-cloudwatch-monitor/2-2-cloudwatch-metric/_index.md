---
title : "Create custom metric"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2.2. </b> "
---
CloudWatch metric provides several metrics for Lambda functions such as the number of times the function is executed, the execution time of each time, error rates, and throttle count. To see the metrics of a certain function we do the following:
1. Open the Lambda function's dashboard
2. Click the function **book-list**
3. Click the **Monitor** tab, select **Metrics**
- Metrics are displayed
4. Next we will create a new metric that sums up the number of hits to DynamoDB that fail
5. Click the **Code** tab, add the following line of code at the top of the function
```
client_cloudwatch = boto3.client('cloudwatch')
```
- Add the following code to the except block of scan DynamoDB table before returning results


```
        client_cloudwatch.put_metric_data(
            Namespace='BooksList_Lambda',
            MetricData=[
                {
                    'MetricName': 'FailedConnectToDynamoDB',
                    'Dimensions': [
                        {
                            'Name': 'env',
                            'Value': 'staging'
                        },
                    ],
                    'Value': 1.0,
                    'Unit': 'Seconds'
                },
            ]
        )
```  
- The code helps you to create a new metric and push the data into it every time the connection to DynamoDB fails

6. Give the function permission to access and push data into metric
7. Call GET API again
8. Open the CloudWatch dashboard
9. Click on Metrics in the left menu, then click **All metrics**
10. In the **Custom namespaces** section appears the metric you created - **BooksList_Lambda**. Click it
11. Press **env**
12. Select **staging**, data display chart
13. You can choose to display parameters according to 1 day or 1 week time, line or number displayed at the top of the graph
So we have created a custom metric. Next step we will use it to create a CloudWatch Alarm