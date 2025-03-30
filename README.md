# aws-networking
## Step 1: Create a VPC
- Sign in to the AWS Management Console.
  
- Navigate to VPC Dashboard (Services > VPC).
  
<img width="1106" alt="cl1" src="https://github.com/user-attachments/assets/7468ffc9-d2fd-448a-a2ba-ec0f0b107fa6" />

- Click Create VPC 
 <img width="1109" alt="cl2" src="https://github.com/user-attachments/assets/68e1b135-04fa-40cb-8d91-9f461fd36b6a" />
 
- Select VPC only.
  
- Enter a descriptive Name
  
- Set the IPv4 CIDR block to 10.0.0.0/16.
  
- Keep IPv6 CIDR as "No IPv6 CIDR block."
  
<img width="1104" alt="cl3" src="https://github.com/user-attachments/assets/0fb8eb21-1b46-4161-bb1f-236ccbddfac2" />

- Enable DNS hostnames and resolution (Optional).
- Click Create VPC
  
<img width="1109" alt="cl4" src="https://github.com/user-attachments/assets/15e25a2d-6671-44ad-9063-738e30b5e817" />

- Yes! Your VPC has been created
  
  <img width="1118" alt="cl6" src="https://github.com/user-attachments/assets/b21bed97-ff43-4940-85ec-b4bd3e0314b2" />
  <img width="1118" alt="cl6" src="https://github.com/user-attachments/assets/b33322e5-d441-4b2f-99f2-13fb12857674" />

## Step 2: Create Subnets in Different Availability Zones
### Create a PUblic Subnet
- Navigate to Subnets in the VPC dashboard.
  
- Click Create subnet.
<img width="1117" alt="cl7" src="https://github.com/user-attachments/assets/cd723a1a-3225-4203-899d-db9944735bb5" />

- Select the VPC ID (aws-networking-vpc).
<img width="1106" alt="cl8" src="https://github.com/user-attachments/assets/06e13b3a-23b0-456f-ae28-f0657a9726a3" />

- Select Public Subnet
  
- Availability Zone: us-east-1a
  
- CIDR Block: 10.0.1.0/24
  
<img width="1108" alt="cl9" src="https://github.com/user-attachments/assets/ca7698df-d25f-4b04-b49f-03f1ba165bae" />


### Create a Private Subnet
- Select private-subnet
  
- Availability Zone: us-east-1b
  
- CIDR Block: 10.0.2.0/24
  
- Navigate down and click Create subnet.
  
<img width="1112" alt="cl10" src="https://github.com/user-attachments/assets/285cbc50-263f-4710-95dc-0f319340bd6f" />

- Boom! Your subnets has been created.
  
<img width="1120" alt="cl11" src="https://github.com/user-attachments/assets/d1d1c778-355e-4daf-be16-a16dd06657b2" />


## Step 3: Attach an Internet Gateway (IGW) to the VPC
- Navigate to Internet Gateways.
  
- Click Create Internet Gateway.
  
<img width="1120" alt="cl24" src="https://github.com/user-attachments/assets/b3ba5d42-91b2-45c2-b3a9-c7b5345b06d9" />

- Enter a descriptive Name.
  
- Click Create Internet Gateway.
  
- Boom! You have successfully created your IGW
  
 <img width="1120" alt="cl14" src="https://github.com/user-attachments/assets/1304abef-93a6-4390-88a0-df08e966525d" />
 
- Select the newly created Internet Gateway.
  
- navigate and Click Attach to VPC,
  
<img width="1120" alt="cl13" src="https://github.com/user-attachments/assets/1c76f092-4f9e-47a0-a3f7-1664418e51d5" />

- choose aws-networking-vpc, and confirm.
  
- Navigate down and click attach internet gateway
  
<img width="1120" alt="cl15" src="https://github.com/user-attachments/assets/332a3c25-7639-475b-9bce-a01e9547e6d1" />

- Now, your internet gateway has successfully been attached
  
<img width="1120" alt="cl16" src="https://github.com/user-attachments/assets/4c5779c2-3b3d-46ff-b3de-f5a2df2d1e42" />

## Step 4: Create and Modify Route Tables
- For the Public Subnet
  
- Navigate to Route Tables
  
- Click Create Route Table.
  
<img width="1125" alt="cl17" src="https://github.com/user-attachments/assets/bdd26f8c-6b87-4a7f-96b5-c7370b2f1edc" />

- Enter:

- Name: public-route-table

- VPC: aws-networking-vpc

- Then click Create.
  
<img width="1120" alt="cl18" src="https://github.com/user-attachments/assets/9695471d-7bb2-48f5-bef3-a779c5a9f5c5" />

- Select public-route-table, go to Routes, and click Edit routes.
  
<img width="1118" alt="cl19" src="https://github.com/user-attachments/assets/7172acb6-27da-43fb-bb65-20282ff0fe42" />

- Add a new route:

- Destination: 0.0.0.0/0

- Target: Select Internet Gateway (IGW).

- Click Save routes.
  
<img width="1120" alt="cl20" src="https://github.com/user-attachments/assets/23706067-6136-439f-9986-3099913b8248" />

- Associate public-subnet with this route table under Subnet associations
  
<img width="1106" alt="cl23" src="https://github.com/user-attachments/assets/084bac78-36db-4d02-8148-7979a188eec0" />

- Select Public-subnet
  
- And then click save association
  
<img width="1120" alt="cl24" src="https://github.com/user-attachments/assets/abe76573-0995-477d-bc1f-c2d6b5c2a5aa" />

- Yes! you have susccessfully associated your public-subnet
  
<img width="1113" alt="cl25" src="https://github.com/user-attachments/assets/3b03f7c3-9cee-426a-8e54-0ec71b8b589d" />


## For the Private Subnet
- Click Create Route Table again.
  
<img width="1119" alt="cl26" src="https://github.com/user-attachments/assets/f54c73ab-d094-4267-99fc-794748c7d6d8" />


- Enter:

- Name: private-route-table

- VPC: aws-networking-vpc

 - Click Create.
<img width="1119" alt="cl27" src="https://github.com/user-attachments/assets/a4643740-045c-44af-adb9-9c17fa8c0bdc" />


- Associate private-subnet with private-route-table.
- 
<img width="1109" alt="cl28" src="https://github.com/user-attachments/assets/df33f9b6-841f-40ae-a200-0ccf635194e2" />

- Select private-subnet
  
- And then click save association
  
<img width="1120" alt="cl29" src="https://github.com/user-attachments/assets/d2ac64fb-7374-479b-96ca-5d40f4cca3b1" />

## Step 5: Set Up a NAT Gateway for Private Subnet
- Navigate to Elastic IPs (Services > EC2 > Elastic IPs).

- Click Allocate Elastic IP Address → Click Allocate.
  
<img width="1120" alt="cl30" src="https://github.com/user-attachments/assets/1bf333fb-8bd1-446c-b5be-f1a91a2788cf" />

- Navigate down and click on Allocate
  
<img width="1109" alt="cl31" src="https://github.com/user-attachments/assets/dcba0528-0c76-49d6-ade4-f5906194b50c" />
<img width="1118" alt="cl32" src="https://github.com/user-attachments/assets/8fe385bb-fdc4-44d1-a56e-2429fc957d16" />

- Navigate to NAT Gateways (Services > VPC > NAT Gateways).
  
- Click Create NAT Gateway.
  
<img width="1120" alt="cl33" src="https://github.com/user-attachments/assets/abb04abf-2934-4ae7-89d1-59f56220c6e0" />

- Select:
- Name: aws-networking-natgw
- Subnet: public-subnet
- Elastic IP: Select the one allocated earlier.

<img width="1117" alt="cl34" src="https://github.com/user-attachments/assets/8d23b164-46fd-4887-b1c4-1481b3b38918" />

- Click Create NAT Gateway and wait for Available status.
  
<img width="1114" alt="cl35" src="https://github.com/user-attachments/assets/8f417135-ac20-4168-898a-33dcbfd4f9de" />
<img width="1120" alt="cl36" src="https://github.com/user-attachments/assets/1f797ff9-bd9d-4fb2-9fe3-4a3591143a56" />

## Modify Route Table for Private Subnet
- Go to Route Tables → Select private-route-table.
- Click Edit routes.
  
<img width="1120" alt="cl37" src="https://github.com/user-attachments/assets/c9712d7c-6151-4bec-8720-1a8505cb86e8" />

- Add:
- Destination: 0.0.0.0/0
- Target: Select NAT Gateway.
- Click Save routes.
  
<img width="1118" alt="cl38" src="https://github.com/user-attachments/assets/446d2123-1841-4d60-96fa-ec1e676b0089" />
<img width="1120" alt="cl39" src="https://github.com/user-attachments/assets/bf6234d8-84be-4eda-a000-c7d46c6cea16" />

## Step 6: Configure Security Group & NACL
### Security Group
- Navigate to Security Groups (Services > EC2 > Security Groups).
- Click Create Security Group.
  
<img width="1123" alt="cl40" src="https://github.com/user-attachments/assets/567b45db-e761-4017-8291-e3c6329fa5e8" />

- Name it web-sg and attach it to aws-networking-vpc.
  
<img width="1103" alt="cl41" src="https://github.com/user-attachments/assets/d12cc383-e26c-4e1a-b8c4-f4cfd6bd0533" />


- Under Inbound rules, add:

- SSH (22), HTTP (80), and HTTPS (443) from 0.0.0.0/0 (or restrict to your IP).

- Under Outbound rules, allow All traffic.

<img width="1106" alt="cl42" src="https://github.com/user-attachments/assets/25f27925-307b-403d-b6a8-f83b902f8d94" />

- Click Create Security Group.
  
<img width="1107" alt="cl43" src="https://github.com/user-attachments/assets/c8bef328-ee70-41bf-8704-469fee673185" />
<img width="1108" alt="cl44" src="https://github.com/user-attachments/assets/2bbadf54-81d7-4fa9-901b-435f7889c1d9" />

## Network ACL (NACL)
- Navigate to Network ACLs (Services > VPC > Network ACLs).

- Click Create Network ACL and attach it to aws-networking-vpc.
  
<img width="1116" alt="cl45" src="https://github.com/user-attachments/assets/df20c228-86e4-491a-92a3-e0d73a0bad94" />

- Click Edit inbound rules, and add:

- Rule 100: Allow SSH (22) from your IP

- Rule 200: Allow HTTP (80) from 0.0.0.0/0

- Rule 300: Allow HTTPS (443) from 0.0.0.0/0

- Click Save changes.
<img width="1117" alt="cl46" src="https://github.com/user-attachments/assets/90987bec-cf65-4570-b3d9-a65809a6985b" />
<img width="1120" alt="cl47" src="https://github.com/user-attachments/assets/1b35247b-5bf4-40ad-b421-7012c2479383" />

## Step 7: Test the Setup
- Launch an EC2 Instance:

- Public Subnet → Assign Public IP

- Private Subnet → No Public IP

- Use web-sg as Security Group



<img width="1107" alt="cl48" src="https://github.com/user-attachments/assets/e966994e-6aef-4d30-a6c5-a269ae716f17" />

- Connect to the Public Instance via SSH.
<img width="1107" alt="cl49" src="https://github.com/user-attachments/assets/ccf9ea6f-00fc-4d59-9951-c1f38eb5e82d" />
<img width="1117" alt="cl50" src="https://github.com/user-attachments/assets/c1e8d2d2-7a43-463b-a5dd-ccc96ddbac75" />






























