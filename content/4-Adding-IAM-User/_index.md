---
title : "Adding a Secondary IAM User"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 4. </b> "
---

#### Introduction

To simulate user interactions and monitor them using AWS CloudTrail, we'll add a secondary IAM user named "workshop2-user" with specific permissions.

#### Step-by-Step Guide to Add the IAM User "workshop2-user"

1. **Access IAM Management Console**: In the AWS Management Console, open the list of all AWS services by choosing **Services**, and locate and choose **IAM**.
   
   ![IAM Management Console](/images/4-adding-iam-user/01-iam-console.png)

2. **Users Section**: In the navigation pane, choose **Users** and then choose **Create user**.
   
   ![Add User](/images/4-adding-iam-user/02-add-user.png)

3. **Enter User Name**: For the User name field, enter `workshop2-user`. Select **AWS Management Console access**

   ![Name User](/images/4-adding-iam-user/03-name-user.png)


4. **Set Access Type**: Choose **I want to create an IAM user**. For Console password, choose **Custom password** and enter a password for the **workshop2-user** user. Clear the **User must create a new password at next sign-in** check box. Choose **Next**.
   
   ![Set Access Type](/images/4-adding-iam-user/04-set-access-type.png)

5. **Attach Policies**: On the **Set permissions** page, choose **Attach existing policies directly**. Search for and select `AmazonEC2FullAccess` and `AmazonS3FullAccess`.
   
   ![Attach Policies](/images/4-adding-iam-user/05-attach-policies.png)
   ![Attach Policies](/images/4-adding-iam-user/06-attach-policies.png)
   ![Attach Policies](/images/4-adding-iam-user/07-attach-policies.png)

6. **Finalize User Creation**: Choose **Next: Tags**, then **Next: Review**, and then **Create user**.
   
   ![Finalize User Creation](/images/4-adding-iam-user/08-finalize-user-creation.png)

7. **Copy IAM Sign-in URL**: After creating the user, copy the displayed IAM sign-in URL. If you missed copying the URL, you can find it on the main IAM page by opening the IAM dashboard.
   
   ![IAM Sign-in URL](/images/4-adding-iam-user/09-iam-url.png)

8. **Log in as "workshop2-user"**: Log out of the AWS Management Console and log back in using the "workshop2-user" user credentials using the sign-in URL. Verify you're logged in as "workshop2-user" by checking the upper-right area of the AWS Management Console.
   
   ![Verify User](/images/4-adding-iam-user/10-verify-user.png)
   ![Verify User](/images/4-adding-iam-user/11-verify-user.png)

9. **Issue API Calls**: Navigate through the AWS Management Console to issue some API calls. **All actions will be captured by CloudTrail**. For example: Navigate to the Ec2 Dashboard, IAM Dashboard or Cloud Trail Dashboard.

{{%notice info%}}
Almost your clicks on screen will make an API call.
{{%/notice%}}

   ![Issue API Calls](/images/4-adding-iam-user/12-issue-api-calls.png)
   ![Issue API Calls](/images/4-adding-iam-user/13-issue-api-calls.png)
   ![Issue API Calls](/images/4-adding-iam-user/14-issue-api-calls.png)

10. **Shut Down an EC2 Instance**: While logged in as "workshop2-user", shut down an EC2 instance. Ensure you don't need the instance or that you created an additional one specifically for this exercise.

   ![Shut Down EC2](/images/4-adding-iam-user/15-shut-down-ec2.png)
   ![Shut Down EC2](/images/4-adding-iam-user/16-shut-down-ec2.png)

11. **Log Back in as Administrator**: Log out as "workshop2-user" and log back in as the administrator to proceed with querying CloudTrail data using Amazon Athena.

{{%notice note%}}
Ensure you remember the password and URL set for the "workshop2-user" as you'll need it to log in.
{{%/notice%}}

13. **Navigate to S3 CloudTrail Bucket**: Access the S3 service and navigate to the CloudTrail bucket (`aws-cloudtrail-logs`). This bucket contains logs of all activities captured by CloudTrail.

   ![S3 CloudTrail Bucket](/images/4-adding-iam-user/17-s3-bucket.png)

14. **Inspect CloudTrail Logs**: Dive deeper into the AWSLogs, followed by your account ID, CloudTrail, the region (e.g., `ap-southeast-1`), and then the specific date. Here, you'll find compressed text files that represent the logged activities.

   ![CloudTrail Logs](/images/4-adding-iam-user/18-cloudtrail-logs.png)

15. **Open a Log File**: Select one of the compressed text files and open it using the "Object actions" option. This will display the raw log data, which can be challenging to interpret directly due to its format and volume.

   ![Open Log File](/images/4-adding-iam-user/19-open-log.png)
   ![Open Log File](/images/4-adding-iam-user/20-open-log.png)
      **Here's the Log**
   ![Open Log File](/images/4-adding-iam-user/21-open-log.png)

{{%notice note%}}
Navigating and analyzing raw CloudTrail logs can be cumbersome, especially during urgent situations where quick insights are needed. The raw logs are not an end-to-end data analytics solution. Instead of manually sifting through raw logs, we can leverage Amazon Athena. Athena allows us to query CloudTrail logs using SQL, providing a more efficient way to extract meaningful insights from the data.
{{%/notice%}}

#### Upcoming Steps

With the "workshop2-user" created and set up, we're now ready to simulate user interactions and monitor them using AWS CloudTrail and Amazon Athena.
