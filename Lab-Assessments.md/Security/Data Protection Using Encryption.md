# Data Protection Using Encryption (AWS KMS)

## Lab Overview

In this lab, I explored how **encryption** protects sensitive data. I created an AWS KMS key and used it on an EC2 instance to encrypt and decrypt text files. This helped me understand how data becomes unreadable once encrypted and only usable again after proper decryption.

---

## Lab Objectives

By the end of this lab, I was able to:

* Create an AWS KMS encryption key
* Install and use the AWS Encryption CLI
* Encrypt plaintext files
* Decrypt encrypted files

---

## Task 1: Creating an AWS KMS Key

I started by searching for **KMS** in the AWS Management Console and opening **Key Management Service**. From there, I chose **Create a key**.

I selected **Symmetric** as the key type and continued with the default configuration. I then added the following details:

* Alias: `MyKMSKey`
* Description: Key used to encrypt and decrypt data files

For key administrators and key usage permissions, I selected **voclabs**, allowing this account to manage and use the key. After reviewing all the settings, I finished creating the key.

Once the key was created, I opened it and copied the **ARN (Amazon Resource Name)**. This ARN was required later when encrypting and decrypting files.

<img width="1071" height="526" alt="lab-2(1)" src="https://github.com/user-attachments/assets/4f5521c6-4f86-413a-8621-55f5a7fb6a7d" />
<img width="1045" height="417" alt="lab-2 (3)" src="https://github.com/user-attachments/assets/b829e58d-50cf-447f-a888-d7d3eb2f47ee" />
<img width="1052" height="496" alt="lab-2 (4)" src="https://github.com/user-attachments/assets/1e860ddb-c993-4015-ada4-ea45dec3247a" />
---

## Task 2: Configuring the File Server EC2 Instance

Next, I opened **EC2** in the AWS Console and selected the **File Server** instance. I connected to it using **Session Manager**, which allowed me to access the Linux terminal directly from the browser.

After connecting, I moved to the home directory and configured the AWS CLI by running:

```bash
cd ~
aws configure
```

When prompted, I entered temporary values and then replaced them with the correct credentials from **Vocareum AWS Details**. I opened the credentials file using nano and replaced its contents with the provided credentials, which included the access key, secret key, and session token.

After saving the file, I verified it using:

```bash
cat ~/.aws/credentials
```

<img width="1116" height="218" alt="lab-2 (5)" src="https://github.com/user-attachments/assets/1c7c98ab-ada7-406e-9d49-ff455fd9d96f" />
<img width="1327" height="476" alt="lab-2 (6)" src="https://github.com/user-attachments/assets/e7f40917-1331-43d7-a064-e252c8e1c4b1" />
<img width="1366" height="728" alt="lab-2 (7)" src="https://github.com/user-attachments/assets/3a972fe9-0062-4007-b405-ff9d69705f38" />


---

## Installing the AWS Encryption CLI

To enable encryption and decryption commands, I installed the AWS Encryption CLI using pip:

```bash
pip3 install aws-encryption-sdk-cli
```

After installation, I updated my PATH so the CLI could be used from anywhere:

```bash
export PATH=$PATH:/home/ssm-user/.local/bin
```
<img width="1366" height="728" alt="lab-2 (8)" src="https://github.com/user-attachments/assets/d36229ce-b2e6-47c9-ba3c-56dd359fa0ea" />


---

## Task 3: Encrypting and Decrypting Data

### Creating the Plaintext Files

I created several text files and added sensitive content to one of them:

```bash
touch secret1.txt secret2.txt secret3.txt
echo 'TOP SECRET 1!!!' > secret1.txt
```

I confirmed the file contents using:

```bash
cat secret1.txt
```

### Encrypting the File

I created an output directory to store the encrypted file:

```bash
mkdir output
```

Using the KMS key ARN I copied earlier, I encrypted the file with the AWS Encryption CLI. Once the command completed successfully, I confirmed that the encrypted file was created inside the output directory.

I then viewed the encrypted file, which appeared unreadable, confirming that the encryption worked as expected.

<img width="1366" height="728" alt="lab-2 (10)" src="https://github.com/user-attachments/assets/0eaf83c6-1122-432e-bff8-6f9427ba5258" />

---

### Decrypting the File

To restore the original content, I ran the decryption command using the same KMS key and encryption context. After the command completed, a decrypted version of the file was generated.

I listed the directory contents and confirmed that the decrypted file was present and readable.

<img width="1366" height="728" alt="lab-2 (11)" src="https://github.com/user-attachments/assets/0d442dc6-bb7b-42fb-b820-f72403d66408" />


---

## Final Outcome

By completing this lab, I successfully encrypted and decrypted sensitive data using **AWS KMS** and the **AWS Encryption CLI**. I clearly observed how encryption protects data by making it unreadable until the correct key and permissions are used.

---

## What I Learned

This lab helped me understand:

* How AWS KMS manages encryption keys
* How encryption protects data at rest
* How to use the AWS Encryption CLI
* The importance of securely managing credentials and permissions

