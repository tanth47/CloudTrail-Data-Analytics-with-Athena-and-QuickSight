---
title : "Visualizing Data in QuickSight"
date : "`r Sys.Date()`"
weight : 6
chapter : false
pre : " <b> 6.2 </b> "
---

#### Introduction

With the dataset in place, we can now proceed to visualize the Athena data in QuickSight. This section will guide you through creating and customizing visualizations.

#### Creating a Custome Dashboard

1. **Access QuickSight Admin Settings**: Navigate to QuickSight and choose **Admin**. In the upper-right corner, select **Manage QuickSight**.
     ![Admin Settings](/images/6-quicksight/6.2-visualizing-data/01-admin-settings.png)

2. **Set Security & Permissions**: On the sidebar, opt for **Security & permissions**. Within the **QuickSight access to AWS services** option, click **Manage**. 
     ![Security Permissions](/images/6-quicksight/6.2-visualizing-data/02-security-permissions.png)
     Here, select **Amazon S3** and choose all the Athena and CloudTrail related buckets.
     ![Security Permissions](/images/6-quicksight/6.2-visualizing-data/03-security-permissions.png)
     ![Security Permissions](/images/6-quicksight/6.2-visualizing-data/04-security-permissions.png)

3. Choose **Save**.
     ![Choose Save](/images/6-quicksight/6.2-visualizing-data/05-chooose-save.png)

4. **Return to Visualization**: Navigate to the upper-left corner and click on the **QuickSight logo**. 
     ![Visualization](/images/6-quicksight/6.2-visualizing-data/06-visualization.png)

5. **Choose Dashboard**: Choose `CloudTrail` dashboard.
     ![Dashboard](/images/6-quicksight/6.2-visualizing-data/07-dashboard.png)

6. **Plot example chart**: In the **Fields list**, select `eventname`. This action will trigger an Athena query, populating a visualization.
     ![Plot example](/images/6-quicksight/6.2-visualizing-data/08-plot-example.png)
{{%notice info%}}
Remember that I am still not filtering by the user. I'm just getting every single API call that is happening in my AWS account. And the reason why PutObject has way more here, is because when CloudTrail adds things to S3, it is doing a PutObject operation
{{%/notice%}}

#### Analyzing Actions of `workshop2-user`

7. **Return to Visualization**: Navigate to the upper-left corner and click on the **QuickSight logo**. 
     ![Visualization](/images/6-quicksight/6.2-visualizing-data/09-visualization.png)

7. **Navigate to Datasets**: From the **QuickSight dashboard**. Choose **Datasets**. Then click **New dataset**.
     ![Datasets](/images/6-quicksight/6.2-visualizing-data/10-datasets.png)


8. **Initiate New Dataset**: Select **Athena**. For the **Data source name**, input `athena2` and confirm with **Create data source**. Choose option for **Use custom SQL**.
     ![Initiate Dataset](/images/6-quicksight/6.2-visualizing-data/11-initiate-dataset.png)
     ![Initiate Dataset](/images/6-quicksight/6.2-visualizing-data/12-initiate-dataset.png)
     ![Initiate Dataset](/images/6-quicksight/6.2-visualizing-data/13-initiate-dataset.png)

9. **Custom SQL for User 'workshop2-user'**: Name the custom SQL query as `workshop2-user-activity`. Insert the following SQL, ensuring to replace `YOUR-ATHENA-TABLE-HERE` with your specific Athena table name:

    ```sql
    SELECT *
    FROM
        cloudtrail_logs_aws_cloudtrail_logs_615700818209_da15e5f3
    WHERE
        useridentity.username LIKE 'workshop2-user';
    ```
     ![Custome SQL](/images/6-quicksight/6.2-visualizing-data/14-custome-sql.png)
     ![Custome SQL](/images/6-quicksight/6.2-visualizing-data/15-custome-sql.png)

10. **Plot Chart**: In `Fields List` choose `useragent`.
     ![Plot chart](/images/6-quicksight/6.2-visualizing-data/16-plot-chart.png)
     Customize **visual type**
     ![Customize chart](/images/6-quicksight/6.2-visualizing-data/17-plot-chart.png)
     We can also add others chart to our dashboard. Example: Click out the dashboard. Then in `Fields list` choose eventname.
     ![Adding chart](/images/6-quicksight/6.2-visualizing-data/18-adding-chart.png)
     **Result**:
     ![Result](/images/6-quicksight/6.2-visualizing-data/19-result.png)
    

{{%notice warning%}}
Remember to unsubscribe from QuickSight after completing these steps to avoid incurring unnecessary costs.
{{%/notice%}}

#### Conclusion

In this section, we delved deep into the actions of the `workshop2-user` by leveraging the power of Amazon QuickSight and Athena. By creating custom datasets and visualizations, we were able to gain insights into the user's activities and interactions with AWS resources. This approach not only simplifies the process of analyzing user actions but also provides a visual representation, making it easier to identify patterns or anomalies. As organizations scale and user activities increase, such visual analytics will be crucial in ensuring smooth operations and security compliance.
