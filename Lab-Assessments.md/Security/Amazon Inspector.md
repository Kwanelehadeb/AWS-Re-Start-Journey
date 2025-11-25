# **Amazon Inspector Lab: Vulnerability Assessment & Remediation**

## **Lab Overview**

In this lab, I use **Amazon Inspector** to scan for vulnerabilities in AWS resources focusing mainly on **AWS Lambda functions**.

I activate Amazon Inspector, review the vulnerability findings, and perform remediation steps to strengthen the security posture.

AnyCompany is building a serverless application using AWS Lambda. They need an automated tool that can:

* Detect vulnerable software packages
* Scan inside Lambda function code
* Automatically scan EC2 instances, Lambda, and ECR images

Amazon Inspector meets these requirements by automatically detecting new deployments and continuously scanning for vulnerabilities.


## **Objectives**

By the end of this lab, I was able to:

* **Activate Amazon Inspector**
* **Analyze and interpret vulnerability findings**
* **Remediate vulnerabilities detected by Amazon Inspector**


## **Lab Steps**

# **Task 1: Activate Amazon Inspector**

In this task, you activate Amazon Inspector so it can continuously scan your Lambda functions.

### **Steps**

1. In the AWS Management Console, search for **Inspector**.
2. Open the left panel and choose **Activate Inspector**.
3. Under *Activate Inspector*, choose **Activate Inspector** again.

<img width="1366" height="768" alt="Screenshot (39)" src="https://github.com/user-attachments/assets/e3b984c3-ba20-45a3-889b-34b816ad9e39" />


4. After activation, a message appears: **“Welcome to Inspector. Your first scan is underway.”**
5. If prompted with the *Feedback for Amazon Inspector* survey, select **Cancel**.
6. Close all banner messages.
7. Refresh the page until **Dashboard → Summary → Environment coverage → Lambda functions** shows **100%**.

<img width="1366" height="768" alt="Screenshot (40)" src="https://github.com/user-attachments/assets/00250d23-b069-4d86-bc1b-6dee1b6e85e4" />


Amazon Inspector automatically scans:

* EC2 instances
* Amazon ECR images
* AWS Lambda functions

---

# **Task 2: Reviewing the Inspected Resources**

While the scan is running, review the current environment to understand what Amazon Inspector is scanning.

## **Task 2.1: Reviewing Your Lambda Functions**

1. On the left menu, choose **Findings → All findings**.
2. Three findings should appear, one for each vulnerability.

You should see:

* **Severity:** Medium
* **Impacted resource:** Your Lambda function
* **Title:** Description of the vulnerability

<img width="1366" height="768" alt="Screenshot (41)" src="https://github.com/user-attachments/assets/2576af0e-c022-456b-8721-c7a1c2c10c2d" />


3. Select the finding **CVE-2023-32681 – requests**.
4. A details pane opens showing information about the vulnerability.
5. Under **Vulnerability details**, select the external link next to **Vulnerability ID**.
6. This opens the National Vulnerability Database (NVD) page with additional details.

<img width="1366" height="768" alt="Screenshot (42)" src="https://github.com/user-attachments/assets/0b92e301-cb8e-4364-b6aa-4f1abf22b96d" />


7. Return to the Inspector pane and scroll to the **Remediation** section.

The issue:
The Lambda function uses an outdated, vulnerable version of the **requests** package.
Amazon Inspector recommends upgrading the package.

# **Task 3: Remediating Vulnerability Findings**

In this task, you fix the vulnerability and confirm that Amazon Inspector detects the remediation.

## **Task 3.1: Updating the Lambda Function Package**

1. In the AWS Console, search for **Lambda**.
2. Select the **get-request** Lambda function.
3. In the file browser, open **requirements.txt**.
4. Replace:

```
requests==2.20.0
```

with:

```
requests
```

(Removing the version number ensures Lambda installs the latest package.)

<img width="1366" height="768" alt="Screenshot (43)" src="https://github.com/user-attachments/assets/f51ab592-1f86-4667-826f-dee21b3c8bad" />


5. Choose **Deploy**.

6. A banner appears: **“Successfully updated the function get-request.”**

7. This triggers Amazon Inspector to automatically initiate a new scan.

8. Return to **Amazon Inspector**.

9. Go to **Findings → All findings**.

10. Change **status** from *Active* to *Closed*.

You should now see **CVE-2023-32681 – requests** listed as *Closed*, confirming successful remediation.

<img width="1366" height="768" alt="Screenshot (44)" src="https://github.com/user-attachments/assets/8a98ae6e-8440-48d1-8679-6a8f82f517f0" />

11. Go to **Resource coverage → Lambda functions**.
12. Expand the **Last scanned** column.
13. You should see an updated timestamp confirming the latest scan.

<img width="1366" height="768" alt="Screenshot (45)" src="https://github.com/user-attachments/assets/8be6b590-0ed1-4d1d-b9fd-0820b0e1c02e" />

## Key Takeaways

Amazon Inspector automatically scans Lambda, EC2, and ECR for vulnerabilities once activated.

Findings include severity levels, affected resources, and links to NVD details for deeper analysis.

Many Lambda vulnerabilities can be fixed by updating outdated dependencies in requirements.txt.

Deploying a Lambda function triggers an automatic rescanning process in Amazon Inspector.

Closed findings confirm that vulnerabilities have been successfully remediated.

## **Summary**

In this lab, I configured Amazon Inspector and learned how it automatically assesses vulnerabilities across AWS resources. I also practiced reviewing findings and applying remediation steps.

This lab strengthened my understanding of **automated security scanning**, **CVE assessment**, and **continuous vulnerability monitoring** in AWS.

