# LINUX Command Line

A short reference for a few basic commands to record session and system metadata.

## Overview
Checks performed are to confirm active user, identify host, record uptime, list sessions, show local times in EST/PST, and get Julian day.

## Commands
```sh
whoami
hostname -s
uptime -p
who -H -a
TZ=America/New_York date
TZ=America/Los_Angeles date
cal -j
```

## Example outputs 
- whoami: `Kwanelehadeb`  
- hostname -s: `ip-10-x-x-x`  
- uptime -p: `up 3 hours, 24 minutes`  
- TZ=America/New_York date: `Sun Nov 23 12:05:06 EST 2025`  
- TZ=America/Los_Angeles date: `Sun Nov 23 09:05:06 PST 2025`  
- cal -j: Julian day for 2025-11-23 = `327`

## Takeaways
- Confirming whoami ensures the session identity is correct.  
- hostname -s ties logs or reports to a specific node.  
- uptime -p quickly reveals how long the system has been running (useful for fault triage).  
- who -H -a shows active sessions and system login history for context.  
- TZ=... date helps compare timestamps across time zones for coordination.  
- cal -j provides a day-of-year useful in scheduling or industry formats.

## Challenges
- Possible time drift: the system clock may be incorrect or unsynchronized, which makes timezone comparisons and logging timestamps unreliable.

## Screenshots 

<img width="1366" height="768" alt="Screenshot (13)" src="https://github.com/user-attachments/assets/3e06ecad-1b66-4f62-9423-0ce360833f04" />
<img width="1366" height="768" alt="Screenshot (14)" src="https://github.com/user-attachments/assets/99ee69b0-b37a-407a-b1c2-b8558656bf56" />
<img width="1366" height="768" alt="Screenshot (16)" src="https://github.com/user-attachments/assets/572997ed-dd2c-4ca5-a6c0-f50b8104953d" />
<img width="1366" height="768" alt="Screenshot (17)" src="https://github.com/user-attachments/assets/0426ed90-79d2-4854-bd13-3feeb2a5fc31" />
<img width="1366" height="768" alt="Screenshot (18)" src="https://github.com/user-attachments/assets/1ca833ba-1dab-494f-92d5-7df19826f075" />
<img width="1366" height="768" alt="Screenshot (19)" src="https://github.com/user-attachments/assets/7a9522c3-2c60-4b21-8d51-8214a733826c" />
<img width="1366" height="768" alt="Screenshot (20)" src="https://github.com/user-attachments/assets/0b1c0a9d-ac30-4f13-9edd-7d2070b56805" />
<img width="715" height="83" alt="Screenshot 2025-11-23 183020" src="https://github.com/user-attachments/assets/9b731399-866a-4422-8e1c-18f33c5cf88f" />
<img width="1366" height="768" alt="Screenshot (21)" src="https://github.com/user-attachments/assets/345909a4-528e-4032-ab61-71f17be73efa" />
<img width="1366" height="768" alt="Screenshot (22)" src="https://github.com/user-attachments/assets/33caa42f-cae1-4154-af82-6e8a387d29d4" />
