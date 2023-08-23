---
title: "Clean Up Resources"
date: "`r Sys.Date()`"
weight: 7
chapter: false
pre: " <b> 7. </b> "
---

Ensuring that you clean up your resources after your experiments or projects is crucial to avoid incurring unnecessary costs. Here's a step-by-step guide to help you clean up the resources used in this workshop:

1. **Amazon QuickSight**:If you no longer plan to use Amazon QuickSight, remember to unsubscribe to avoid any charges.
   - Navigate to `Manage QuickSight`.
    ![Unsubcribe QS](/images/7-clean-up/01-clean-up.png)
   - Click `Delete account`.
    ![Unsubcribe QS](/images/7-clean-up/02-clean-up.png)
   - Type `confirm` and click `Delete account`.
    ![Unsubcribe QS](/images/7-clean-up/03-clean-up.png)
   - Unsubscribe successful.
    ![Unsubcribe QS](/images/7-clean-up/04-clean-up.png)

2. **Amazon Athena**:
   - Go to the [Athena console](https://console.aws.amazon.com/athena/).
   - In the `Query Editor`, find and delete the tables you've created for this workshop.
    ![Clean up Athena](/images/7-clean-up/05-clean-up-athena.png)
   - Type table name and click `Delete`.   
    ![Clean up Athena](/images/7-clean-up/06-clean-up-athena.png)   
   - Complete 
    ![Clean up Athena](/images/7-clean-up/07-clean-up-athena.png)   

3. **Amazon S3**:
   - Access the [S3 console](https://console.aws.amazon.com/s3/). Locate and delete the S3 buckets associated with this workshop. 
   - Choose Bucket and click `Empty`.
    ![Clean up S3](/images/7-clean-up/08-clean-up-s3.png)  
   - Type `permanently delete` and click `Empty`.
    ![Clean up S3](/images/7-clean-up/09-clean-up-s3.png)  
   - Choose Bucket and click `Delete`.
    ![Clean up S3](/images/7-clean-up/10-clean-up-s3.png)  
   - Type bucket name and click `Delete`.
    ![Clean up S3](/images/7-clean-up/11-clean-up-s3.png)  
   - Successfully deleted bucket
    ![Clean up S3](/images/7-clean-up/12-clean-up-s3.png)  
   - Do the same manner for the rest.

4. **IAM Roles and Users**:
   - Visit the [IAM console](https://console.aws.amazon.com/iam/).
   - Delete any roles or users (`workshop2-user` and others) that were specifically created for this workshop.
    ![Delete IAM User](/images/7-clean-up/13-delete-iam-user.png)  
 
5. **Amazon EC2** (if used):
   - Open the [EC2 console](https://console.aws.amazon.com/ec2/).
   - Terminate any instances that were launched for this workshop. Also, remember to release any associated Elastic IPs to avoid charges.
    ![Terminate Ec2 Instance](/images/7-clean-up/14-terminate-ec2-instance.png)  


6. **CloudTrail**:
   - Navigate to the [CloudTrail console](https://console.aws.amazon.com/cloudtrail/).
   - Navigate to `Dashboard` and open the trail you created.
    ![Delete CloudTrail](/images/7-clean-up/15-delete-cloud-trail.png)  
   - Click on `Delete` and hit `Delete` again.
    ![Delete CloudTrail](/images/7-clean-up/16-delete-cloud-trail.png)  

#### Conclusion

You've successfully cleaned up all the resources you created during this workshop. It's always a good practice to delete unused resources to avoid incurring unnecessary costs.
