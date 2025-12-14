# Working with AWS Lambda – Sales Analysis Report

## Lab Overview

In this lab, I worked with **AWS Lambda** to build a serverless system that automatically generates and emails a daily sales report.
The solution pulls sales data from a MySQL database running on an EC2 LAMP server, processes the data using Lambda functions,
and sends the final report to an administrator by email.

The main goal of this lab was to understand how different AWS services work together in a serverless architecture, especially Lambda, IAM, SNS, CloudWatch, Systems Manager Parameter Store, and VPC networking.

---

## Understanding the Architecture (In My Own Words)

The process starts with a scheduled event and ends with an email report:

Every evening, CloudWatch triggers a Lambda function called **salesAnalysisReport**.
This function does not directly access the database. Instead, it calls another Lambda function named **salesAnalysisReportDataExtractor**,
which is responsible for connecting to the MySQL database and running analytical queries.

The data extractor function retrieves database credentials securely from **AWS Systems Manager Parameter Store**,
connects to the café database, and runs a query to collect sales information. Once the data is collected, it is sent back to the main Lambda function.

The main function then formats the data into a readable sales report and publishes it to an **SNS topic**. Finally, SNS delivers the report to the administrator via email.
<img width="773" height="415" alt="lab-2 (1)" src="https://github.com/user-attachments/assets/ca4e1506-a8ff-477b-aff9-367addb65967" />


---

## Objectives of the Lab

By completing this lab, I learned how to:

* Identify the correct IAM permissions needed for Lambda functions
* Create and use Lambda layers for external libraries
* Build Lambda functions that interact with databases
* Schedule Lambda executions using CloudWatch (EventBridge)
* Use CloudWatch logs to troubleshoot Lambda errors

---

## Challenges I Faced

This was the most challenging lab I worked on. I repeatedly encountered an **“Execution result: failed”** error during testing,
which was frustrating because the lab instructions suggested it should work immediately.

After troubleshooting, I realized the issue was related to **network access**. Although I had created inbound rules for port **3306**,
the Lambda function still could not connect to the database. I went back to the Lambda configuration, checked the VPC settings, and reviewed the EC2 security group rules.
Once I added the missing inbound rule allowing MySQL traffic on port 3306, the issue was resolved.

When I ran the test again, I finally saw the green message **“Execution result: succeeded (logs)”**, which confirmed that the function was working correctly.

---

## Task 1: Reviewing IAM Roles

### salesAnalysisReportRole

I opened IAM and reviewed the role used by the main Lambda function. I confirmed that Lambda was trusted to assume this role.
The attached policies allowed the function to:

* Publish messages to SNS
* Read values from Parameter Store
* Write logs to CloudWatch
* Invoke another Lambda function

This role is used by the **salesAnalysisReport** function.



### salesAnalysisReportDERole

I then reviewed the role for the data extractor function. This role allows Lambda to write logs and access resources inside a VPC.
This is required so the function can connect to the EC2-hosted MySQL database.


---

## Task 2: Creating a Lambda Layer and Data Extractor Function

### Creating the Lambda Layer

I created a Lambda layer named **pymysqlLibrary** and uploaded the provided `pymysql-v3.zip` file. This layer contains the PyMySQL library, which is required for connecting to the MySQL database. I set Python 3.9 as the compatible runtime.

  <img width="1336" height="498" alt="lab-2 (3)" src="https://github.com/user-attachments/assets/54c56634-9d05-459a-bfd0-4b3654595934" />


### Creating the Data Extractor Lambda Function

Next, I created a Lambda function named **salesAnalysisReportDataExtractor** using Python 3.9. I selected an existing IAM role and attached **salesAnalysisReportDERole**.

<img width="1350" height="513" alt="lab-2 (5)" src="https://github.com/user-attachments/assets/c824dbdf-325e-4f84-b214-94cb91eb6e5f" />


### Attaching the Layer and Uploading Code

I attached the PyMySQL layer to the function and updated the handler setting.
I then uploaded the `salesAnalysisReportDataExtractor-v3.zip` file containing the function code.

<img width="1366" height="499" alt="lab-2 (8)" src="https://github.com/user-attachments/assets/d9228758-1162-4706-8b6c-9f53f68eb8fe" />

Then I choose Add to attach the layer to my function.

### Configuring VPC Access

To allow the function to reach the database, I configured the function to run inside the **Cafe VPC**, selected a public subnet, and attached the café security group.

<img width="1350" height="516" alt="lab-2 (14)" src="https://github.com/user-attachments/assets/327f1ea5-d31d-4da2-b24a-6713dceec258" />


---

## Task 3: Testing the Data Extractor Function

I retrieved the database connection values from **AWS Systems Manager Parameter Store** and used them in a test event inside the Lambda console.
After fixing the security group issue, the test ran successfully.

To generate real data, I accessed the café website using the EC2 public IP address and placed several orders.
After adding data, I ran the test again and confirmed that the function returned updated results.



---

## Task 4: Configuring Notifications with SNS

I created an SNS topic called **salesAnalysisReportTopic** and subscribed my email address to it.
After confirming the subscription through email, the topic was ready to deliver reports.

<img width="1366" height="432" alt="lab-2 (19)" src="https://github.com/user-attachments/assets/d2fd0514-2872-4ba9-a154-6b974f634e47" />
    Task 4.2: Subscribing to the SNS topic

---

## Task 5: Creating the Main Sales Report Lambda Function

Using the CLI Host EC2 instance, I configured the AWS CLI and created the **salesAnalysisReport** Lambda function from a ZIP file.
I then added an environment variable containing the SNS topic ARN.

After testing the function successfully, I added a scheduled trigger using **EventBridge (CloudWatch Events)** so the report runs automatically from Monday to Saturday.
<img width="1360" height="406" alt="lab-2 (26)" src="https://github.com/user-attachments/assets/c1b49ea7-bff4-487a-95d2-4c1b75d4c8bc" />
<img width="1366" height="728" alt="Screenshot 2025-12-03 135234" src="https://github.com/user-attachments/assets/8e2b9adc-cff2-42e8-b7ff-a6512eb2eeb8" />


---

## Final Outcome

The system now automatically generates a daily sales analysis report and emails it to the administrator.
I can place new orders on the café website and see updated data reflected in future reports.

---

## Key Takeaways

Through this lab, I learned how to design a serverless workflow using AWS services. I gained hands-on experience with IAM permissions, Lambda layers, database connectivity, scheduled triggers, and troubleshooting using CloudWatch logs.
Despite the challenges, completing this lab significantly improved my confidence in working with AWS Lambda.



