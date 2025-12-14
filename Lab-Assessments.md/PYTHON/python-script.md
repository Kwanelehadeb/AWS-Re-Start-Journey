# Python Script: Prime Numbers 

## Lab Overview

In this lab, I worked on a Python scripting exercise where I created a program to identify all prime numbers between **1 and 250**. The goal of the lab was to practice writing Python scripts on a Linux system while using functions, loops, and file handling.

---

## Tools and Environment

* **Language:** Python 3
* **Operating System:** Linux (EC2 instance)
* **Editor:** nano
* **Connection Method:** SSH (PuTTY)

---

## Steps I Followed

### 1. Connecting to the Server

I configured **PuTTY** to connect to the EC2 instance using **SSH**. After connecting, I logged in as the **ec2-user** to access the Linux terminal.

<img width="1577" height="826" alt="image" src="https://github.com/user-attachments/assets/1f4ac352-d250-4f64-8c16-bdb0a7c55c10" />
<img width="652" height="420" alt="image" src="https://github.com/user-attachments/assets/28c4d9b1-7460-4462-a22a-f26610ba68be" />
---

### 2. Creating the Python Script

Once logged in, I created a new Python file named:

```
prime_numbers.py
```

I used the **nano** text editor to create and edit the file by running:

```bash
nano prime_numbers.py
```
<img width="654" height="420" alt="image" src="https://github.com/user-attachments/assets/f12a156d-e3b1-4e73-b63e-8e9913984c0b" />

 <img width="718" height="515" alt="image" src="https://github.com/user-attachments/assets/14e530f7-3311-4f7a-aad6-679ad82d2780" />

<img width="658" height="412" alt="image" src="https://github.com/user-attachments/assets/66ea1394-f9b9-49f9-995d-f1c31e81e294" />


---

### 3. Writing the Prime Number Logic

Inside the script, I created a function that checks whether a number is prime. The function works by testing if a number can be divided evenly by any value starting from 2 up to the number itself.

I then wrote the main part of the program using a loop that goes through numbers **1 to 250**. Each number was checked using the prime-checking function, and all prime numbers were stored in a list.

<img width="665" height="417" alt="image" src="https://github.com/user-attachments/assets/05691096-5800-4eaa-ba5f-ea424a359cfd" />



### 4. Displaying Output and Writing to a File

After identifying the prime numbers, I displayed them in the terminal using the `print()` function.

I also added file handling so that the results could be saved permanently. I created a file called:

```
results.txt
```

Using Python’s file handling methods (`open()`, `write()`, and `close()`), the script writes all the prime numbers into this file.


### 5. Saving and Running the Script

After finishing the code, I saved the file in nano by pressing **Ctrl + X**, then **Y**, and **Enter**.

I ran the script using:

```bash
python3 prime_numbers.py
```

### 6. Verifying the Results

To confirm that the output was saved correctly, I viewed the contents of the results file using:

```bash
cat results.txt
```

The output confirmed that **53 prime numbers** were correctly identified and stored.

I also checked the absolute path of the script using:

```bash
realpath prime_numbers.py
```

This helps with locating the script later.

<img width="666" height="419" alt="image" src="https://github.com/user-attachments/assets/fefcb45c-79e8-4440-9657-b257c002ef87" />

<img width="657" height="414" alt="image" src="https://github.com/user-attachments/assets/41c8cef7-3d4e-41a5-8783-59a802cacccf" />

<img width="657" height="415" alt="image" src="https://github.com/user-attachments/assets/1cb77dc9-1c8d-45bc-9dc2-ddbd486515cd" />

---

## Challenges Faced

* **File handling:** I initially forgot to close the file after writing to it. This helped me understand why the `close()` method is important to ensure data is saved properly.

---

## What I Learned

* How to create and edit Python scripts using the **nano** text editor
* The importance of correct indentation and syntax in Python
* How to use functions and loops to process numerical data
* How to write output to external files using Python file handling
* How to run Python scripts from the Linux command line



