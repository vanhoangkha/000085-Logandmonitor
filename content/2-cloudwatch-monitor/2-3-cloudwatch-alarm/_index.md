---
title : "Creating Alerts with CloudWatch Alarm"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 2.3. </b> "
---
1. Open the dashboard of [CloudWatch]()
2. Expand **Alarms** on the left side, press **In alarm**
3. Press **Create alarm**
4. Press **Select metric**
5. Select the metric created in the previous step - **BooksList_Lambda**, then press **env**, then select **staging**
- Press **Select metric**
6. Select **Sum** for **Statistic**
7. Set the condition in the item condition
- Select **Static** for **Threshold type**
- Select **Greater/Equal** as the warning condition
- Enter **2** as the value of the alarm threshold
8. Click **Next**
9. Select **Create new topic**
10. Enter the topic name
12. Enter the email you want to receive notifications for
13. Click **Create topic**
14. Scroll down, click **Next**
15. Enter a name for the alert
- Click **Next**
16. Scroll to the bottom and press **Create alarm**
17. Back to Postman's screen, press **Send** twice to call the API twice
18. Open email and check
19. Back to the CloudWatch dashboard
20. Click **All alarms**, then select the alarm you just created
21. The histogram of the metric is displayed