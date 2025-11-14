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

