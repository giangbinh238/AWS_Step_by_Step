# JumpBox

JumpBox (also called Bastion)

## Principle: 

- Jumbox in **public** subnet
- Final Instance in **private** subnet
- **--> if JB is shut down - nobody can access EC2.**

## Architecture:

![Image of architecture](https://github.com/giangbinh238/AWS_Step_by_Step/blob/master/JumpBox/Image/Architecture_diagram.png)

## Step 1 : VPC
- Created VPC : `10.10.0.0/16`
## Step 2 : Subnet
- Created 2 Subnet link to the VPC with /24 IPv4 CIDR Block within one AZ
- Subnet1_GeeBee (Public Subnet) : `10.10.1.0/24`
- Subnet2_GeeBee (Private Subnet): `10.10.2.0/24`
![Image of subnet](https://github.com/giangbinh238/AWS_Step_by_Step/blob/master/JumpBox/Image/Capture1.PNG)
## Step 3 : Internet Gateway
- Create Internet Gateway and attach to the VPC 
## Step 4 : EC2 Instances
Create 3 EC2 Instances

1.NAT Instance (in Public Subnet)
- Using "amzn-ami-vpc-nat" for AMI
- Disable Change Source/Dest.Check (Actions > Networking > Change Source/Dest. Check > Yes, Disable).
- Security Groupe : `NATSG` with the configuration 

Inbound Rule

|Type     | Protocol  | Port Range  | Source |
| ---------- |-----| -----|----------------------|
|SSH    |TCP | 22 | 10.10.2.0/24 |
|HTTP      | TCP | 80 | 10.10.2.0/24 |
|HTTPS      | TCP | 443 | 10.10.2.0/24 |
| ALL ICMP-IPv4	| All | N/A | 10.10.2.0/24 |

Outbound Rule 

|Type     | Protocol  | Port Range  | Source |
| ---------- |-----| -----|----------------------|
|SSH    |TCP | 22 | 10.10.2.0/24 |
| ALL ICMP-IPv4	| All | N/A | 0.0.0.0/0 |
  
![Image of NAT Instance](https://github.com/giangbinh238/AWS_Step_by_Step/blob/master/JumpBox/Image/Capture11.PNG)

2.Jumpbox (in Public Subnet) : 

Inbound rule
To IWG

![Image of Jumpbox](https://github.com/giangbinh238/AWS_Step_by_Step/blob/master/JumpBox/Image/Capture9.PNG)

3.Databases Instance (In Private Subnet):
To The Nat instance (or subnet)
![Image of Databases Instance](https://github.com/giangbinh238/AWS_Step_by_Step/blob/master/JumpBox/Image/Capture10.PNG)

## Final Step : Result Ping to Google.com
![Image of ConnecttoEC2](https://github.com/giangbinh238/AWS_Step_by_Step/blob/master/JumpBox/Image/ConnectToEC2.PNG)
