## 1. What is Amazon EC2?

EC2 = Elastic Compute Cloud

Provides virtual servers in the cloud.

You choose CPU, memory, storage, OS.

Scalable (scale up/down anytime).

Pay only for what you use.

## 2. Main Components of EC2
AMI (Amazon Machine Image)

Template used to launch an instance (OS + software).

## Instance Types

General Purpose – balanced (t3, t4g).

Compute Optimized – high CPU (c5, c6g).

Memory Optimized – RAM-heavy workloads (r5, x1).

Storage Optimized – high IOPS (i3, d2).

Accelerated Computing – GPUs/ML (p3, g4).

## Storage Options

EBS = persistent block storage.

Instance Store = temporary (lost on stop/terminate).

## Networking

VPC, Security Groups, ENI (network card).

## Key Pair

SSH access to the instance.

## User Data

Script that runs at first boot (automation).

## 3. EC2 Purchasing Options
## On-Demand

Pay per hour/second.

Flexible, no commitment.

Best for short workloads.

## Reserved Instances

1 or 3-year commitment.

Up to 75% cheaper.

Best for steady workloads.

## Spot Instances

Up to 90% cheaper.

Can be interrupted anytime.

Best for batch jobs, big data, CI/CD.

## Dedicated Host

Dedicated physical server.

Compliance or licensing needs.

## Dedicated Instances

Hardware isolated to a single customer.

## Capacity Reservation

Reserve capacity in a specific AZ.

No long-term commitment.

## 4. EC2 Instance Connect

Browser-based SSH access.

No need for local SSH keys.

Uses IAM permissions.

## 5. Security Groups

Virtual firewall for EC2.

Controls inbound & outbound traffic.

Stateful → return traffic allowed automatically.

Only allow specific ports (e.g., SSH = 22, HTTP = 80).
