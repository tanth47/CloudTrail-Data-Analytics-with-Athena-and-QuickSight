---
title : "CloudTrail Data Analytics with Athena and QuickSight"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
---
# CloudTrail Data Analytics with Athena and QuickSight

#### Objective
In this workshop, participants will explore the depth of AWS CloudTrail's data analytics capabilities. Utilizing Amazon Athena and Amazon QuickSight, we'll transform raw CloudTrail logs into insightful visualizations.

#### Scenario:
As an AWS administrator, you're tasked with monitoring and analyzing user interactions across various AWS services. AWS CloudTrail captures these events, and you aim to query, analyze, and visualize this data to gain actionable insights.

#### Brief Overview
Participants will journey through the AWS landscape, starting with CloudTrail event capture, querying this data with Athena, and finally visualizing the insights using QuickSight.

![CloudTrailAnalytics](/images/Architecture.png) 

#### Key Components:
- **AWS CloudTrail:** Captures AWS service events.
- **Amazon S3:** Stores the CloudTrail logs.
- **Amazon Athena:** Queries the CloudTrail logs stored in S3.
- **Amazon QuickSight:** Visualizes the data fetched from Athena.

#### Content
 1. [Introduction](1-introduction/)
 2. [Preparation](2-preparation/)
 3. [Creating a CloudTrail](3-creating-cloudtrail/)
 4. [Adding a Secondary IAM User](4-adding-iam-user/)
 5. [Investigating with Amazon Athena](5-athena/)
 6. [Visualizing Athena Data in Amazon QuickSight](6-quicksight/)
 7. [Clean Up Resources](7-clean-up)

#### Duration:
Approximately 45 minutes
