---
title : "Investigating with Amazon Athena"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 5. </b> "
---

#### Introduction

To investigate AWS resource interactions, we'll use Amazon Athena. Athena allows us to create tables pointing to S3 buckets, facilitating the querying of CloudTrail logs.

#### Step-by-Step Guide to Investigate with Amazon Athena

1. **Access CloudTrail in AWS Management Console**: Navigate to the list of all AWS services by choosing **Services**, and locate and choose **CloudTrail**.

2. **Navigate to Event History**: In the navigation pane, choose **Event history** and then select **Create Athena table**.
   ![Event History](/images/5-athena/01-event-history.png)

3. **Choose Storage Location**: For **Storage location**, select the bucket you created during the CloudTrail configuration. This action updates the SQL command to use the appropriate bucket location.
   ![Storage Location](/images/5-athena/02-storage-location.png)

4. **Create Athena Table**: Click on **Create table**. You now have an Athena table structured like CloudTrail and pointing to the S3 bucket used by CloudTrail.
   ![Create Athena Table](/images/5-athena/03-create-athena-table.png)

5. You now have an Athena table with the same schema that is used by CloudTrail. The table points to the recently created S3 bucket that is used by CloudTrail.
   ![Create Athena Table](/images/5-athena/04-succeed.png)

5. **Access Athena in AWS Management Console**: Return to the list of AWS services, locate and choose **Athena**.

6. **Configure Athena Settings**: If it's your first time using Athena, configure the settings. In the upper-right corner, choose **Settings**. Then, select an S3 bucket for Athena query results. A suitable bucket might already exist, often named starting with `aws-athena-query-results`.
   ![Configure Athena](/images/5-athena/05-configure-athena.png)

7. **Query Result Storage**: Select another S3 bucket for the Athena query result location by choosing the Select button. A bucket might have been automatically created for this purpose, so you might only need to select a bucket with a name that starts with aws-athena-query-results.
   ![Query Result Storage](/images/5-athena/06-query-result-storage.png)
   ![Query Result Storage](/images/5-athena/07-query-result-storage.png)
   ![Query Result Storage](/images/5-athena/08-query-result-storage.png)


8. **Run Queries**: With Athena set up, you can run SQL queries to analyze CloudTrail logs. For instance, to get the activity history of an EC2 instance, use the provided SQL query, replacing placeholders with your specific details.
   ```sql
   SELECT *
   FROM
       YOUR-ATHENA-TABLE-HERE
   WHERE 
       eventsource = 'ec2.amazonaws.com' AND 
       requestparameters LIKE '%YOUR-INSTANCE-ID-HERE%' AND
       responseelements != 'null';
   ```
   You can find you table name here:
   ![Run Queries](/images/5-athena/09-run-queries.png)

   Here's example result:
   ![Run Queries](/images/5-athena/10-run-queries.png)


{{%notice note%}}
The power of Athena lies in its ability to quickly query vast amounts of data. By converting CloudTrail logs into structured tables, we can derive insights more efficiently than sifting through raw logs.
{{%/notice%}}

9. **Tracking user action**: This query should reveal that the "workshop2-use" user issued an API call that shut down the web server. The following query shows you the other actions that "workshop2-user" did in the AWS account:
   ```sql
   SELECT *
   FROM
      YOUR-ATHENA-TABLE-HERE
   WHERE
      useridentity.username LIKE 'workshop2-user';
   ```
   ![Tracking user action](/images/5-athena/11-tracking-user-action.png)

#### Upcoming Steps

With the insights derived from Athena, we can visualize this data in Amazon QuickSight, such as creating pie charts of successful and failed requests. The next section will delve into creating these visualizations.
