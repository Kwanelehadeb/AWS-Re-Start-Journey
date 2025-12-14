# Hello World Python Lab (AWS Cloud9)

## Lab Overview

This lab is my introduction to programming using Python. I used the AWS Cloud9 IDE to create and run my first Python program. The purpose of this lab was to confirm that the Python environment is working correctly.

## Lab Objectives

* Access the AWS Cloud9 IDE
* Create a Python file
* Check installed Python versions
* Write and run a Hello World program



## Steps Performed

### 1. Accessing AWS Cloud9

I started the lab and waited until the status showed **Lab ready**. From the AWS Management Console, I opened **Cloud9** and launched the environment called `reStart-python-cloud9`.
<img width="1366" height="768" alt="Screenshot (51)" src="https://github.com/user-attachments/assets/e559f780-3d28-44ad-b277-8e97a7d8b8fd" />

---

### 2. Creating the Python File

I created a new Python file using the template option, removed the sample code, and saved the file as:

```
hello-world.py
```

The file was saved in the default Cloud9 directory:

```
/home/ec2-user/environment
```

<img width="1366" height="768" alt="Screenshot (52)" src="https://github.com/user-attachments/assets/8977e112-efe7-463f-b1dc-1ad2e618b46d" />


---

### 3. Using the Terminal

I opened a new terminal in Cloud9 and confirmed my working directory using:

```bash
pwd
```

This confirmed that I was working in the correct folder.

<img width="1109" height="115" alt="Screenshot 2025-12-14 214303" src="https://github.com/user-attachments/assets/c57e4e4a-0f64-4443-8b5c-e7090a01e0d5" />


---

### 4. Checking Python Versions

To make sure Python was installed, I checked the available versions using:

```bash
python --version
python2 --version
python3 --version
```

Python 3.6 was available and used for this lab.

<img width="1366" height="768" alt="Screenshot (53)" src="https://github.com/user-attachments/assets/4c01f0bd-f058-477c-9d1e-a46cfe117f28" />


---

### 5. Writing and Running the Program

Inside `hello-world.py`, I wrote the following code:

```python
print("Hello, World")
```

After saving the file, I ran the program using the **Run** button in Cloud9. The output displayed **Hello, World**, confirming that the program executed successfully.

<img width="905" height="136" alt="Screenshot 2025-12-14 215745" src="https://github.com/user-attachments/assets/4e9a6710-e289-4db4-8973-5acb17aac28e" />


---

## Challenges and Solutions

## Challenges
- Cloud9 warning pop-ups   
- Multiple Python versions
  

## Solutions
-Selected Discard when prompted
-Verified and used Python 3

## What i have learned
I have successfully created and ran my first Python program using AWS Cloud9. This lab helped me understand how to work with the IDE, terminal, and basic Python syntax.
