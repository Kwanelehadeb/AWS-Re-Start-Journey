# EC2 Launch Lab

## Summary 
This lab is about to launch, manage, resize, and monitor an Amazon EC2 instance.

## Objectives
- Learn how to launch an EC2 instance 
- Verify instance health and system status.
- Update security group rules to allow HTTP traffic.
- Resize instance type and increase root volume storage.
- Test termination protection.

## Tasks performed
1. Launched an EC2 instance
   - choosing AMI(Amazon Linux 2023)
   - Instance type: t3.micro (initial)
3. Verified instance health
   - Checked CPU utilization and system status checks to confirm the instance was running correctly.
4. Updated security group
   - Added an HTTP (port 80) inbound rule so the web server could be accessed from the internet.
5. Resized the instance
   - Changed instance type from `t3.micro` to `t3.small`.
   - Increased root volume size from 8 GB to 10 GB and resized the filesystem as needed.
6. Tested termination protection
   - Enabled termination protection and attempted to terminate the instance; AWS blocked the action as expected.

## Challenges
- No major challenges ,the steps were straightforward.

## Takeaways
- Always set correct and minimal security group rules for the services you expose.
- Enable termination protection when working with important instances you do not want accidentally terminated.
- Remember to resize the filesystem after increasing EBS volume size.

## Screenshots
<img width="1366" height="768" alt="Screenshot (3)" src="https://github.com/user-attachments/assets/86eda35c-eea5-4070-bad0-333215069ddc" />
<img width="1366" height="768" alt="Screenshot (4)" src="https://github.com/user-attachments/assets/7af195bf-f7e9-4bbe-81f2-e0fd3fe937dc" />
<img width="1366" height="768" alt="Screenshot (5) - Copy" src="https://github.com/user-attachments/assets/6653ea1c-475f-4240-b494-4dff317315e3" />
<img width="1366" height="768" alt="Screenshot (6) - Copy" src="https://github.com/user-attachments/assets/8900a15e-709f-416b-bf13-0d02d987ac03" />
<img width="1366" height="768" alt="Screenshot (7)" src="https://github.com/user-attachments/assets/8e7499b8-9a56-4b38-a155-dc276804aba1" />
<img width="1366" height="768" alt="Screenshot (8)" src="https://github.com/user-attachments/assets/26eea616-386e-49bf-a573-a45863f8fb72" />
<img width="1366" height="768" alt="Screenshot (9)" src="https://github.com/user-attachments/assets/4e7990fc-50e8-455e-8a37-dd18560b68e1" />
<img width="1366" height="768" alt="Screenshot (10)" src="https://github.com/user-attachments/assets/cd53c5e2-c177-49f5-85cf-229573939730" />
