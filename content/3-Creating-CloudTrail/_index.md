---
title : "Creating a CloudTrail"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 3. </b> "
---

#### Introduction

AWS CloudTrail is a service that enables governance, compliance, operational auditing, and risk auditing of your AWS account. In this section, we'll configure CloudTrail to capture and log events related to our AWS resources.

#### Step-by-Step Guide to Configure CloudTrail

1. **Access CloudTrail Management Console**: Navigate to the [CloudTrail service administration interface](https://console.aws.amazon.com/cloudtrail/).
   
2. **Create a New Trail**: Click on **Create trail**.
   
   ![Create Trail](/images/3-configuring-cloudtrail/01-create-trail.png)

3. **Name your Trail** Provide a name for your trail, for instance, `WorkshopTrail`.

   ![Name Trail](/images/3-configuring-cloudtrail/02-name-trail.png)

3. **Set S3 Bucket**: In the **Trail log bucket and folder** box, keep the default name suggestion.
   
   ![Set S3 Bucket](/images/3-configuring-cloudtrail/03-set-s3-bucket.png)

{{%notice note%}}
S3 bucket is the bucket where CloudTrail will store information. Make sure that you copy this bucket name because you will need it when you create the Amazon Athena table. For example: `aws-cloudtrail-logs-615700818209-da15e5f3`
{{%/notice%}}

4. **Configure Settings**: Disable **Log file SSE-KMS encryption**. Scroll down and click **Next**.
   
   ![Configure Settings](/images/3-configuring-cloudtrail/04-configure-settings.png)
   ![Configure Settings](/images/3-configuring-cloudtrail/05-next-configuring.png)

5. **Choose log events**: On the next page, select **Management events**, **Data events** and **Insights events**.

   ![Log Events](/images/3-configuring-cloudtrail/06-log-events.png)

6. **Data Events**: Storage using **S3** and we will log all events.

   ![Data Events](/images/3-configuring-cloudtrail/07-data-events.png)

7. **Insight Events**: 

   ![Insight Events](/images/3-configuring-cloudtrail/08-insight-events.png)

{{%notice info%}}
CloudTrail Insights, additional charges apply, because it's doing some sort of machine learning under the hood.
{{%/notice%}}

8. **Next**: Scroll down to the bottom of the page and choose **Next**.

   ![Choose Next](/images/3-configuring-cloudtrail/09-next-review.png)

9. **Finalize CloudTrail Configuration**: Review all settings and click **Create** to finalize the CloudTrail configuration.
   
   ![Finalize Configuration](/images/3-configuring-cloudtrail/10-finalize-config.png)

10. **Creating CloudTrail successfully**

   ![Created the CloudTrail](/images/3-configuring-cloudtrail/11-created-cloudtrail.png)


#### Upcoming Steps

With CloudTrail configured, we're now set to capture AWS events and further analyze them using tools like Amazon Athena.
