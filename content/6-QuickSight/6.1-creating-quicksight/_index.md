---
title : "Creating QuickSight Account and Dataset"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 6.1 </b> "
---

#### Introduction

In this section, we'll guide you through the initial setup of Amazon QuickSight, from accessing the service to creating a dataset from Athena.

#### Step-by-Step Guide to Create QuickSight Account and Dataset

1. **Access QuickSight in AWS Management Console**: Navigate to AWS Management Console, locate and choose **QuickSight**.

2. **Sign Up for QuickSight**: If it's your first time, sign up for a subscription. Choose the **Standard subscription** and proceed.
   ![Sign Up](/images/6-quicksight/6.1-creating-quicksight/01-sign-up.png)
   ![Standard subscription](/images/6-quicksight/6.1-creating-quicksight/02-standard-subscription.png)

3. **Enter QuickSight Account Details**: Provide a globally unique name for the QuickSight account (e.g., `workshop2-quicksight`). Enter a valid email address. For AWS services, select **Amazon S3** and choose all related Athena and CloudTrail buckets.
   ![Account Details](/images/6-quicksight/6.1-creating-quicksight/03-account-details.png)

4. **Grant QuickSight S3 Access**: Scroll down to **QuickSight access to AWS services**. Add Amazon S3 and select all related Athena and CloudTrail buckets. 
   ![S3 Access](/images/6-quicksight/6.1-creating-quicksight/04-s3-access.png)
   ![S3 Access](/images/6-quicksight/6.1-creating-quicksight/05-s3-access.png)

5. After all, hit **Finish**. Your QuickSight account will be created and ready to use. To start creating visualizations, choose **Go to Amazon QuickSight**.

   ![Finish Create](/images/6-quicksight/6.1-creating-quicksight/06-hit-finish.png)

6. **Create New Dataset**: In the navigation pane, choose **Datasets**and then **New dataset**.
   ![New Dataset](/images/6-quicksight/6.1-creating-quicksight/07-new-dataset.png)
   Select **Athena** as the data source.
   ![New Dataset](/images/6-quicksight/6.1-creating-quicksight/08-new-dataset.png)
   Name it `athena1`, and proceed.
   ![New Dataset](/images/6-quicksight/6.1-creating-quicksight/09-new-dataset.png)
   Choose the Athena table related to CloudTrail then hit **Select**.
   ![Select Athena Table](/images/6-quicksight/6.1-creating-quicksight/10-select-athena-table.png)
   Change option to **Directly query your data**.
   ![Select Athena Table](/images/6-quicksight/6.1-creating-quicksight/11-select-athena-table.png)   

#### Upcoming Steps

After setting up your QuickSight account and creating the initial dataset, the next phase involves diving deeper into data visualization. In the subsequent section, you'll:

- Create specific visualizations based on the Athena data.
- Customize these visualizations to gain meaningful insights.
- Create a dedicated dataset to filter and focus on specific user activities.
- Convert visual data representations, like transforming bar charts into pie charts for better clarity.

