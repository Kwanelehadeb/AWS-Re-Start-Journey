### PHYTHON -SCRIPT
- I worked through a Python programming lab where I created a script to identify prime numbers between 1 and 250.
-   Learning about functions, loops, and file handling.

### STEPS I TOOK 

<img width="1577" height="826" alt="image" src="https://github.com/user-attachments/assets/1f4ac352-d250-4f64-8c16-bdb0a7c55c10" />

### **CONFIGURE YOUR PUTTY USING SSH TO CONNECT**
## - LOG IN AS EC2-USER !!!

<img width="652" height="420" alt="image" src="https://github.com/user-attachments/assets/28c4d9b1-7460-4462-a22a-f26610ba68be" />

### CREATING THE PHYTHON SCRIPT
- Created a Python script file using the nano text editor by executing nano prime_numbers.py in the Linux terminal.

 <img width="654" height="420" alt="image" src="https://github.com/user-attachments/assets/f12a156d-e3b1-4e73-b63e-8e9913984c0b" />

 <img width="718" height="515" alt="image" src="https://github.com/user-attachments/assets/14e530f7-3311-4f7a-aad6-679ad82d2780" />

<img width="658" height="412" alt="image" src="https://github.com/user-attachments/assets/66ea1394-f9b9-49f9-995d-f1c31e81e294" />

### WRITTING THE PRIME NUMBER LOGIC
- I wrote a prime-checking function that tests whether a number is prime by checking for divisibility from 2 up to the number itself.
- Then I implemented the main logic using a loop to iterate through numbers 1 to 250.
- Applied the prime-checking function to each number and storing the results in a list.

<img width="665" height="417" alt="image" src="https://github.com/user-attachments/assets/05691096-5800-4eaa-ba5f-ea424a359cfd" />

### Adding Output and File Writing
- Added output functionality to display the prime numbers in the console using the `print()` function.
-  Then I configured file writing to save `results to results txt`.
-  Using Python's file handling methods `(open(), write(), and close())`.

-  ### Saving and Running the Script
- I saved the script in nano by pressing `Ctrl+X`.
- Confirming with `Y`, and pressing `Enter`.
- Then I executed the script using the command `python3 prime_numbers.py.`

### Verifying the Results
- I verified the results by viewing the contents of results.txt using the cat command.
- Which confirmed that all 53 prime numbers were successfully identified and stored.
- Documented the script location by obtaining the absolute path using `realpath prime_numbers.py` for future reference.

<img width="666" height="419" alt="image" src="https://github.com/user-attachments/assets/fefcb45c-79e8-4440-9657-b257c002ef87" />

<img width="657" height="414" alt="image" src="https://github.com/user-attachments/assets/41c8cef7-3d4e-41a5-8783-59a802cacccf" />

<img width="657" height="415" alt="image" src="https://github.com/user-attachments/assets/1cb77dc9-1c8d-45bc-9dc2-ddbd486515cd" />

### The script successfully identified 53 prime numbers and saved them to the results file as required.

### WHAT I LEARNED
Here's what I learned from this challenge:

- I created a Python script using the nano text editor and learned the importance of proper indentation and syntax in Python.
- I implemented a prime number algorithm that identifies all prime numbers between 1 and 250 by checking for divisibility.
- I used Python's file handling methods to write results to a text file for permanent storage.

#### CHALLENGES
- File Handling Syntax: I struggled with properly closing the file after writing to it.
-  I forgot to include the close() method initially, which could have caused issues with data not being saved properly to results..txt

###  OVERALL
- I learned how to write and execute Python scripts on Linux,
- Process numerical data. 
- Save output to external files using the command line.

### Lab Complete 🎓










