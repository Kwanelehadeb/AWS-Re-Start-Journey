# Creating Networking Resources in an Amazon Virtual Private Cloud (VPC)
## Objectives
- Summarize the customer scenario
- Create a VPC, Internet Gateway, Route Table, Security Group, Network Access List, and EC2 instance to create a routable network within the VPC
- Familiarize yourself with the console
- Develop a solution to the customers issue found within this lab. 

  
## Task 1: Investigate the customer's needs

- I open the AWS console from Vocareum and then access the VPC service either from Recently visited services or by selecting it under Networking and Content Delivery in the Services menu.
- Start at the top of the left navigation pane at Your VPCs and work your way down. Select Your VPCs, navigate to the top right corner, and select Create VPC
- Name the VPC: Test VPC
- IPv4 CIDR block: 192.168.0.0/18
- Leave everything else as default, and select Create VPC.
  
 ## **Creating Subnets**
- Now that the VPC is complete, look at the left navigation pane and select Subnets. In the top right corner, select Create subnet.

<img width="1862" height="322" alt="lab-2(2)" src="https://github.com/user-attachments/assets/3626e02f-020e-48c6-8d73-32a43c6f607c" />

   *Figure: Select Create subnet*

Configure like the following picture:

<img width="775" height="858" alt="lab-2(3)" src="https://github.com/user-attachments/assets/50e48577-501d-4622-8567-d872997eb518" />

 ## Create Route Table
 
 Navigate to the left navigation pane, and select Route Tables. In the top right corner select Create route table.
<img width="1873" height="344" alt="lab-2(4)" src="https://github.com/user-attachments/assets/7d0ba6cb-4193-4675-b0e4-6810dc08c37f" />
   
 Configure like the following picture:  

<img width="899" height="824" alt="lab-2(5)" src="https://github.com/user-attachments/assets/ff41ff71-10bc-488d-a9fe-c7e2d92ba8d9" />

   
  ## Create Internet Gateway and attach Internet Gateway
  
From the left navigation pane, select Internet Gateways. Create an Internet Gateway (IGW) by selecting Create internet gateway at the top right corner.

<img width="1872" height="377" alt="lab-2(6)" src="https://github.com/user-attachments/assets/dacb8cde-cb71-48a6-b803-c2306154cef9" />


Configure like the following picture:

<img width="904" height="735" alt="lab-2(7)" src="https://github.com/user-attachments/assets/e384c28d-7975-4667-ab7f-f84c7f48698b" />


Once created, attach the Internet Gateway to the VPC by selecting Actions at the top right corner and clicking Attach to VPC.

<img width="1606" height="380" alt="lab-2(8)" src="https://github.com/user-attachments/assets/fb01cf1d-f733-48fa-af77-450b776ea504" />

## Add route to route table and associate subnet to route table

I go to the Public Route Table, add a new route with destination 0.0.0.0/0, set its target to the Internet Gateway, and save the changes so internet-bound traffic can reach the IGW.

<img width="1820" height="468" alt="lab-2(9)" src="https://github.com/user-attachments/assets/9aeb262e-6799-426f-a682-2d85ad42f5fb" />



From the Public route table dashboard, select the Subnet associations tab. Select the Edit subnet associations button

<img width="1840" height="608" alt="lab-2(10)" src="https://github.com/user-attachments/assets/fcffa273-4841-4187-996d-1496076a013d" />


Select Save assocation.

## Creating a Network ACL

From the left navigation pane, select Network ACLs. Navigate to the top right corner and select Create network ACL to create a Network Access Control Lists (NACLs).

<img width="1863" height="828" alt="lab-2(11)" src="https://github.com/user-attachments/assets/31b8ada2-ebdf-4b52-99a8-d12e1d6adabb" />


On the Create network ACL, configure the following:
  - Name: Public Subnet NACL
  - VPC: Choose Test VPC from dropdown
  - Choose Create network ACL
    
On the Network ACLs option, from the list of ACLs select Public Subnet ACL

From the tabs below, select Inbound rules and then choose Edit inbound rules

On the Edit inbound rules, choose Add new rule and configure:
   - Rule number: Enter 100
   - Type: Choose All traffic from dropdown
   

Back on the  Network ACLs option, ensure that Public Subnet ACL is selected

Choose Outbound rules and then choose Edit outbound rules

On the Edit outbound rules, choose Add new rule and configure:
     - Rule number: Enter 100
     - Type: Choose All traffic from dropdown
     

## Creating a Security Group

From the left navigation pane, select Security Groups. Navigate to the top right corner and select Create security group to create a security group.

<img width="1920" height="531" alt="lab-2(12)" src="https://github.com/user-attachments/assets/d4558b2a-ba27-4661-b8f3-c73b0d69c6df" />


Configure like the following image of the Basic details page:

<img width="719" height="350" alt="lab-2(13)" src="https://github.com/user-attachments/assets/493c6e70-409b-4ea8-a11a-7e77c2322579" />


The finished security group allows inbound SSH, HTTP, and HTTPS traffic from anywhere, and it allows all outbound traffic from the instance. Make sure everything is configures just like the following in your security groups:

<img width="1753" height="745" alt="lab-2(14)" src="https://github.com/user-attachments/assets/1d28ede1-75d7-47a4-8ac3-1cb3598a6c09" />


## Task 2: Launch EC2 instance and SSH into instance
I open the EC2 service from the AWS console and then go to the Instances section in the left navigation pane.
Choose Launch instances and configure the following options:
 - In the Name and tags section, leave the Name blank.
 - In the Application and OS Images (Amazon Machine Image) section, configure the following options:
 - Quick Start: Choose Amazon Linux.
 - Amazon Machine Image (AMI): Choose Amazon Linux 2023 AMI.
 - In the Instance type section, choose t3.micro.
 - In the Key pair (login) section, choose vockey.

In the Network settings section, choose Edit and configure the following options:
 - VPC - required: Choose Test VPC. 
 - Subnet: Choose Public Subnet.
 - Auto-assign public IP: Choose Enable.
 - Firewall (security groups): Choose Select existing security group.
 - Choose public security group.
 - Choose Launch instance.
## Task 3: Use ping to test internet connectivity
- I ran the following command to test internet connectivity: ping google.com
- After a few seconds, exit ping by holding CTRL+C on Windows or CMD+C on Mac to exit.I got the the following result:

Successful ping:

<img width="664" height="178" alt="ping" src="https://github.com/user-attachments/assets/63f195a1-c4aa-4883-bf0f-e255bbe5c0a0" />


 #  What i have learned
   - Create a Amazon Virtual Private Cloud (Amazon VPC) and understand how to create subnets and allocate IP addresses

   
