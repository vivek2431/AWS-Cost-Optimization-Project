# AWS-Cost-Optimization-Project

## Overview

This project provides a Lambda function to identify and delete stale Amazon Elastic Block Store (EBS) snapshots in AWS. Stale snapshots, which are no longer associated with active EC2 instances, are identified and removed to optimize storage costs.

## Description

The Lambda function fetches all EBS snapshots owned by the same account ('self') and retrieves a list of active EC2 instances (running and stopped). For each snapshot, it checks if the associated volume, if it exists, is not associated with any active instance. If a stale snapshot is identified, it is deleted, effectively optimizing storage costs.

## Features

- **Stale Snapshot Identification**: Automatically identifies EBS snapshots not associated with any active EC2 instance.
- **Optimized Storage Costs**: Deletes stale snapshots to reduce storage costs.
- **Customizable Configuration**: Adjust the Lambda function settings based on specific requirements.

## Prerequisites
- AWS account with necessary permissions.
- AWS EC2 Instance, Volume, Snapsho
- AWS Lambda
- AWS IAM

## Steps

- **Open AWS Console**
- **Go to EC2 Instance**
- **Launch EC2 instance by the name of "testec2server"**

 ![one](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/695904af-1494-4f60-b77a-73b6c14c57b8)
 
 ![two](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/ed7da290-867a-44dc-bd7d-34f29ce294c9)

 ![three](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/95fbe8f9-16d7-4d72-b068-4373da46f768)

 - **Select "Ubuntu Server"**
 - **Instance type "t2.micro"**
 - **Select Key pair "myworkplace1"**
 - **Keep everything at default**
 - **Then Click "Launch Instance"**

 ![four](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/acb2ef3f-4471-480d-9cee-b1f548ea7e11)

 ![six](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/39ef6d61-c420-4659-9e50-3d8e439237c9)

 ![40](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/0e952bae-f3aa-4e91-91f1-6a2a7f3b6fc0)

 - **Go to Snapshots**
 - **Create Snapshot**
 - **Select the volume option and associate the volume**
 - **Click create snapshot**
 
 ![41](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/c730e8ad-59f7-4af1-adf8-9cb49876f32d)

 ![42](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/221729d6-b0c3-4997-988b-0066db347e2c)

 ![43](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/3da75331-e112-4c6d-86e3-43179807c329)

 ![44](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/b8ed1bb0-b21e-4e32-9382-fa42d271d909)

 - **Go to AWS Lambda**
 - **Select Create Function**
 - **In function name "cost-optimization-ebs-snapshot"**
 - **Runtime select "python3.10"**
 - **Keep Everything Default**
 - **Click "create function"**

 ![twelve](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/c8b06440-b24c-41bd-8b7f-f86cec72da4e)

 ![thirteen](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/d5ef5f3e-c26f-4908-9874-eb988ff47e73)

 ![fifteen](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/87149bc7-efdf-4011-acb2-67c7bbc2b738)

 ![sixteen](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/292aedf0-325b-4a2b-b4af-d4bbd8ca0d67)

  - **Deploy your code in the code section**
  - **Configure the test Event**
  - **Test the Code**

 ![seventeen](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/7d5023a3-9658-42f2-8177-ee38c34bd954)

 ![nineteen](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/ddfbce1b-2c65-43cb-9e6a-40e55707e555)

 ![20](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/efbeeefa-e8d4-4020-9090-3ef377bf3167)

 - **It will show error**
 - **Go to configuration**
 - **General configuration click "edit"**
 - **Increase the timeout from "3 seconds to 10 seconds"**

 ![21](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/1482513b-b9b1-4f78-abe6-5acd1c0d6e01)

 ![22](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/444a7d6d-3fed-4eb1-a4fb-5639ea95843d)

 ![45](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/cc27ea99-e78d-4d37-9127-abee89e2a54f)

 - **Go to permissions**
 - **click "Role Name"**
 - **In role Section, Go to "AWSlambdaexecutionrole"**
 - **Select "add permission"**
 - **Select Attach policy**
 
 ![46](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/568672d9-1969-40f7-bea2-d2a59e1d68d8)

 ![47](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/75381686-993b-4544-a046-d29e1dd45376)

 - **Select Service as "EC2"**
 - **In filter Section write "Snapshot"**
 - **In list section search & Select "Describesnapshot"**
 - **In write section search & select "Deletesnapshot"**
 - **Again in filter section write "Describe"**
 - **Select "Describevolume"**
 - **Select "Describeinstance"**
 - **In policy name write "cost-optimization-ebs"**

 ![29](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/61390686-5279-425a-8f2d-82c4f94f466b)

 ![31](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/daa12938-8d11-4f3c-8847-6b2bd3762535)

 ![32](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/f7a36e3e-84ad-48fe-bbea-3d6f548bf510)

 ![33](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/e28a3c01-77f3-4e0a-90ba-cff875ac0725)

 ![34](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/e35005ac-ce59-46dc-86bc-433a6789edea)

 ![35](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/5f2a8ec8-55a0-4c14-af52-543738e04dcc)

  - **Attach policy "cost-optimization-ebs" to role "AWSlambdaroleexecution"**
  - **click the "test" option in AWS lambda**

 ![48](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/d2dd511c-f070-4164-b8c6-015585725bdf)

 ![49](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/7ade8e11-91c0-402e-8098-aa8fc3491589)

 - **terminate your "testec2server"**
 - **Delete your volume as well"**
 - **snapshot is not deleted yet**

 ![50](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/46a42f06-cb5b-4a07-9fc0-6b0c26496281)

 ![53](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/cb8e706e-09b1-4455-a2ff-f5c5a7293401)

  -  **in the lambda code there is a if and else statement which emphasizes The Lambda function fetches all EBS snapshots owned by the same account ('self') and also retrieves a list of active EC2 instances (running and stopped). For each snapshot, it checks if the associated volume (if exists) is not associated with any active instance. If it finds a stale snapshot, it deletes it, effectively optimizing storage costs**

 ![55](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/714c57a1-2165-49d8-813a-7652f1e2080c)

 ![60](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/0047f764-b1a2-4484-9e10-a4289eb087df)

 ![59](https://github.com/vivek2431/AWS-Cost-Optimization-Project/assets/137812531/9b911f66-3fcc-4d08-b66e-0a15f3fd7e15)

  ## Key Achievements
  
  - **Automated Stale Snapshot Identification**: The Lambda function seamlessly fetches all EBS snapshots owned by the account and cross-references them with active EC2 instances. This automated process ensures accurate identification of stale snapshots.

  - **Dynamic Configuration**: The Lambda function is highly customizable, allowing users to configure parameters such as the AWS region, dry-run mode, and optional snapshot tag filters. This flexibility enables users to tailor the solution to their specific needs.

  - **Cost Savings**: By automatically deleting stale snapshots that are no longer associated with active instances, the project contributes to significant cost savings in storage expenses. This proactive approach aligns with AWS best practices for resource optimization.

 ## Usage
  Deploy the Lambda function, configure triggers (e.g., CloudWatch Events), and let the solution run on a scheduled basis. Monitor the Lambda function logs for snapshot identification and deletion activities. The project is designed to seamlessly integrate into existing AWS environments with minimal effort.

## Future Enhancements

The project can be further enhanced with additional features and improvements:

- **Snapshot Archiving**: Integrate a mechanism to archive snapshots instead of immediate deletion, providing an additional layer of data protection.
- **Extended Tag Filtering**: Expand the filtering capabilities to include more sophisticated tag-based filtering for snapshots.
- **Enhanced Logging**: Implement detailed logging and reporting mechanisms to provide insights into the cost savings achieved over time.
  
## Conclusion
The AWS Cloud Cost Optimization - Identifying Stale EBS Snapshots project offers an efficient solution for managing and reducing storage costs associated with Amazon Elastic Block Store (EBS) snapshots. By automating the identification and deletion of stale snapshots, this project aims to optimize resources and enhance cost efficiency within AWS environments.
    






  
   
  
    






 
    



 





 







 










  



