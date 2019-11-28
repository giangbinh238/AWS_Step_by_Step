# JumpBox
## Step 1 : VPC
- Created VPC : `10.10.0.0/16`
## Step 2 : Subnet
- Created 2 Subnet link to the VPC with /24 IPv4 CIDR Block within one AZ
- Subnet1_GeeBee (Public Subnet) : `10.10.1.0/24`
- Subnet2_GeeBee (Private Subnet): `10.10.2.0/24`
![Image of subnet](https://github.com/giangbinh238/AWS_Step_by_Step/blob/master/JumpBox/Image/Capture1.PNG)
## Step 3 : Internet Gateway
- Create Internet Gateway and attach to the VPC 
## Step 5 :EC2 Instances
Create 3 EC2 Instances : 
- NAT Instance (in Public Subnet) : 
  ...Using "amzn-ami-vpc-nat" for AMI 
  ...disable Change Source/Dest.Check (Actions > Networking > Change Source/Dest. Check > Yes, Disable)
  
![Image of NAT Instance](https://github.com/giangbinh238/AWS_Step_by_Step/blob/master/JumpBox/Image/Capture11.PNG)

- Jumpbox (in Public Subnet) : 
![Image of Jumpbox](https://github.com/giangbinh238/AWS_Step_by_Step/blob/master/JumpBox/Image/Capture9.PNG)

- Databases Instance (In Private Subnet):
![Image of Databases Instance](https://github.com/giangbinh238/AWS_Step_by_Step/blob/master/JumpBox/Image/Capture10.PNG)

## Result
![Image of ConnecttoEC2](https://github.com/giangbinh238/AWS_Step_by_Step/blob/master/JumpBox/Image/ConnectToEC2.PNG)
