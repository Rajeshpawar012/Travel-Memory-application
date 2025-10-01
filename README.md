# Travel-Memory-application

• The Travel Memory application has been developed using the MERN stack and is running on an Amazon EC2 instance.

### Workflow Diagram:

<img width="3244" height="1692" alt="image" src="https://github.com/user-attachments/assets/6390ec2f-d312-4761-8370-2bf0d8b2b518" />


## Launch EC2 Instance

• Go to the AWS EC2 Console.

• choose Amazon Linux 

• Instance type t2.micro(free tier eligible)

• launch Instance.

## Connect to EC2 Instance via ssh

• Command: 

- ssh -i .\herokey2822.pem ec2-user@ec2-18-171-251-128.eu-west-2.compute.amazonaws.com

## install Dependencies 

- sudo yum update

<img width="941" height="281" alt="image" src="https://github.com/user-attachments/assets/a8792665-b2e9-4b19-ab25-479d0bbf0ac6" />

- sudo yum install git -y

<img width="946" height="357" alt="image" src="https://github.com/user-attachments/assets/d151f213-0bfd-44f4-832d-3f12908bb938" />

### Clone Git repository

- git clone https://github.com/Rajeshpawar012/TravelMemory.git

- ls

- TravelMemory

- cd TravelMemory

<img width="778" height="172" alt="image" src="https://github.com/user-attachments/assets/3ce7cf6e-2c1a-483c-a449-3c7d473706b3" />

- sudo yum install nodejs -y

<img width="939" height="320" alt="image" src="https://github.com/user-attachments/assets/ba4c3d16-b244-4d6c-988a-fe63c49cee7a" />

## MongoDB Atlas Integration

### steps to connect your backend to MongoDB Atlas:

### 1. Create a MongoDB Atlas Cluster

- Go to MongoDB Atlas

- Sign in or create an account

- Create a new cluster (choose free tier if eligible)

- rajesh-mongo-cluster
 
- Select a cloud provider and region close to your EC2 instance

<img width="957" height="511" alt="image" src="https://github.com/user-attachments/assets/93083e7f-3a24-4f50-ac96-ac2c7b4e9c69" />

<img width="914" height="470" alt="image" src="https://github.com/user-attachments/assets/e6d23c89-6942-45c3-9fe3-34db6b602712" />


### 2. Configure Network Access

- Add your EC2 instance's public IP to the IP whitelist

- Alternatively, allow access from anywhere (0.0.0.0/0) for testing

<img width="956" height="447" alt="Screenshot 2025-09-30 230626" src="https://github.com/user-attachments/assets/7f4d4635-defc-4019-a87d-9ebaaa03acda" />


### 3. Create a Database User

- Go to *Database Access*

- Create a user with a username and password

- Username: rajeshpawar012_db_user

- Password: sS6yWqsKlL0fUjf3

- Assign read and write access to your database

<img width="795" height="420" alt="image" src="https://github.com/user-attachments/assets/a1ee3e64-4797-46e4-8bdd-2e00831b892e" />


### 4. Get the Connection String

- Go to *Clusters > Connect > Connect your application*

- Copy the connection string (mongodb+srv://rajeshpawar012_db_user:************@rajesh-mongo-cluster.mddajai.mongodb.net/?retryWrites=true&w=majority&appName=rajesh-mongo-cluster)

<img width="915" height="451" alt="Screenshot 2025-09-30 231449" src="https://github.com/user-attachments/assets/085029ec-2b35-4cd8-9da9-b8cec5a21271" />


### 5. Update .env File in Backend

Create or update the .env file in the backend directory:

PORT=3001

MONGO_URI=mongodb+srv://rajeshpawar012_db_user:sS6yWqsKlL0fUjf3@rajesh-mongo-cluster.mddajai.mongodb.net/?retryWrites=true&w=majority&appName=rajesh-mongo-cluster

- sudo npm install mongodb

<img width="604" height="114" alt="image" src="https://github.com/user-attachments/assets/969896e3-e813-4adb-b943-5e177503bc1c" />

-sudo nano .env

<img width="858" height="190" alt="Screenshot 2025-09-30 233542" src="https://github.com/user-attachments/assets/502799d7-f177-436c-83fc-9424a848bf75" />

### Enter MongoDB connection URI in .env file.

MONGO_URI='mongodb+srv://rajeshpawar012_db_user:sS6yWqsKlL0fUjf3@rajesh-mongo-cluster.mddajai.mongodb.net/?retryWrites=true&w=majority&appName=rajesh-mongo-cluster/travelDB'

PORT=3001


<img width="957" height="527" alt="image" src="https://github.com/user-attachments/assets/cbd7030d-a45f-40af-82fc-b4cebb5eff7f" />


### Then enter command 

- head package.json

<img width="615" height="272" alt="image" src="https://github.com/user-attachments/assets/dfa89fc4-347b-42dc-bebe-f9db2b268791" />

### enter command npm install command

- npm install

<img width="619" height="230" alt="image" src="https://github.com/user-attachments/assets/59c6a362-1f7c-42d5-bc1e-9fdd51a81979" />

### Cat index.js

-cat index.js 

<img width="707" height="293" alt="image" src="https://github.com/user-attachments/assets/4e8ac64d-f5f9-45fa-ab1c-8763e1c173aa" />

### cat command for package.json

-cat package.json

<img width="802" height="299" alt="image" src="https://github.com/user-attachments/assets/95e4bf32-d5c3-4a0d-b6e9-b8527460efcf" />

### start backend server

-sudo node index.js

<img width="518" height="30" alt="image" src="https://github.com/user-attachments/assets/5d3c3371-b551-4d4b-a78d-5f5873a7000c" />

#### backend server started

###Frontend Configuration

#### Open New Tab and connect to frontend instance and navigate to frontend directory

- ssh -i .\herokey2822.pem ec2-user@ec2-18-175-210-159.eu-west-2.compute.amazonaws.com

-cd TravelMemory

-cd frontend

### install Dependancy

run Sudo npm install

- sudo npm install

<img width="942" height="502" alt="Screenshot 2025-10-01 002724" src="https://github.com/user-attachments/assets/cee11057-601a-4fe3-a3c3-93eebe199d0a" />

<img width="746" height="329" alt="Screenshot 2025-10-01 003005" src="https://github.com/user-attachments/assets/627ee443-f833-4b4d-85e0-cc1b953beda0" />


- Sudo nano src/url.js

<img width="823" height="85" alt="Screenshot 2025-10-01 003531" src="https://github.com/user-attachments/assets/4d5ccd8c-d637-4c1d-b7ef-ea4fba1e639b" />


- Add public IP of backendip:portal

- export const baseUrl = process.env.REACT_APP_APP || "http://13.40.109.184:3001";

<img width="956" height="539" alt="Screenshot 2025-10-01 003602" src="https://github.com/user-attachments/assets/c7f348ca-7aa9-4724-9be9-9332d9ee2d77" />

- Save it 

Run sudo npm start

- sudo npm start

 <img width="582" height="351" alt="Screenshot 2025-10-01 003935" src="https://github.com/user-attachments/assets/e8497900-4e2e-4e0d-937d-cc86e1c6156e" />

<img width="503" height="89" alt="image" src="https://github.com/user-attachments/assets/df4aa497-9a24-444c-a7ab-f6bb590ae7f9" />

### Procedure to access your app

- copy public DNS of CE2 instance and paste it on the browser and add :3000 port

 ec2-13-40-109-184.eu-west-2.compute.amazonaws.com:3000

<img width="953" height="531" alt="Screenshot 2025-10-01 004127" src="https://github.com/user-attachments/assets/a07f13b2-f116-4e29-a672-32ca156ce6bf" />

<img width="944" height="446" alt="Screenshot 2025-10-01 004929" src="https://github.com/user-attachments/assets/856243ef-dab8-47c8-8c81-0880b4728d76" />

<img width="957" height="504" alt="Screenshot 2025-10-01 005629" src="https://github.com/user-attachments/assets/dc9bf436-d501-4236-8c56-96864b740d6d" />

<img width="952" height="505" alt="Screenshot 2025-10-01 010051" src="https://github.com/user-attachments/assets/2a847020-9082-48b1-a7e8-84cedf88c3af" />

<img width="959" height="482" alt="Screenshot 2025-10-01 005002" src="https://github.com/user-attachments/assets/46322632-0789-420e-8584-4309be02ffa0" />



## Step to Scaling the Application

### Launch Multiple EC2 Instances

#### Create AMI from Existing Instance

. 	Go to EC2 Dashboard → Instances.
 	
. 	Select your configured instance (frontend or backend).
	
. 	Click Actions → Image → Create Image.
 	
. 	Name the AMI (Rajesh-travelmemory-image ).
	
. 	Wait for the AMI to be available under AMIs.
	
### Launch New Instances from AMI

. 	Go to Launch Instance.
 	
. 	Choose your custom AMI.

. 	Select instance type (t2.micro).
	
##	Configure instance details:

• 	Set Auto-assign Public IP to Enable.

• 	Add to appropriate security group (allow ports 80 and 3000).

. 	Launch multiple instances ( 2 frontend, 2 backend).

<img width="581" height="126" alt="Screenshot 2025-10-01 154219" src="https://github.com/user-attachments/assets/ca12a7af-cc2f-4faf-986a-d9a97b84c571" />


## Set Up Target Groups

#### Create Target Groups

. 	Go to EC2 → Target Groups → Create Target Group.

. 	Choose Instances as target type.

. 	Create two groups:

• 	 (port 80)

• 	 (port 3000)

<img width="749" height="44" alt="Screenshot 2025-10-01 153456" src="https://github.com/user-attachments/assets/a7690b12-a428-45fc-9c8d-9c3dd144b168" />

. 	Register instances:

• 	Add frontend EC2s to 

• 	Add backend EC2s to 

### Create Application Load Balancer

 Configure Load Balancer

. 	Go to EC2 → Load Balancers → Create Load Balancer.

. 	Choose Application Load Balancer.

. 	Set	Name: 

• 	Scheme: Internet-facing

• 	Listeners: Port 80

. 	Select VPC and subnets (at least 2 for high availability).

<img width="743" height="53" alt="Screenshot 2025-10-01 153412" src="https://github.com/user-attachments/assets/2c0e2eed-e38d-4cf1-9fa6-5432034570b1" />

 ####Add Listeners and Rules

. 	Listener on port 80:

• 	Default rule → forward to 

. 	Add rule:

• 	If path is  → forward to 


## a step-by-step guide to purchase a domain from Namecheap:

### How to Purchase a Domain from Namecheap

#### Visit Namecheap

Go to https://www.namecheap.com

#### Search for Your Domain

• 	Use the search bar on the homepage.

• 	Type in your desired domain name (rajeshtravelmemory).

• 	Click Search.

#### Choose Your Domain

• 	Browse available options.

• 	Look for .in, .com, .online, or other extensions.

• 	Click Add to Cart next to your preferred domain.

<img width="952" height="506" alt="Screenshot 2025-10-01 130102" src="https://github.com/user-attachments/assets/ed051107-f93d-42c9-877d-8c95d9a5f114" />


#### Review Your Cart

• 	Click the Cart icon in the top-right corner.

• 	Review pricing and term (default is 1 year).

<img width="946" height="503" alt="Screenshot 2025-10-01 130425" src="https://github.com/user-attachments/assets/f16614cd-1ee5-409e-b277-815b8386303d" />

• 	You can optionally add:

• 	Domain privacy protection (usually free with Namecheap)

• 	SSL certificate (optional for now—Cloudflare provides free SSL)

<img width="895" height="510" alt="Screenshot 2025-10-01 132246" src="https://github.com/user-attachments/assets/08514ca6-8ea2-46af-9e2d-8efabe8c76a0" />


#### Create an Account

• 	Click Checkout.

• 	Sign up for a Namecheap account or log in if you already have one.

#### Complete Payment

• 	Enter your billing details.

• 	Choose a payment method (credit/debit card, PayPal, etc.).

• 	Click Pay Now to complete the purchase.

<img width="943" height="449" alt="Screenshot 2025-10-01 133003" src="https://github.com/user-attachments/assets/118a858f-5dc3-46bd-a5e1-8874545933b4" />


#### Access Your Domain

• 	After payment, go to Dashboard → Domain List.

• 	You’ll see your new domain listed there.

### Next Steps

•   Once you’ve purchased the domain:

• 	Add it to your Cloudflare account.

• 	Update the nameservers in Namecheap to point to Cloudflare’s.

• 	Set up DNS records (A and CNAME) in Cloudflare.

<img width="956" height="427" alt="Screenshot 2025-10-01 134714" src="https://github.com/user-attachments/assets/1aca3b1c-e5ad-4646-b076-9383fe110ce3" />



Here’s a complete guide to setting up your domain with Cloudflare after purchasing it from a registrar like Namecheap:

# Cloudflare Setup Steps After Buying a Domain

## Create a Cloudflare Account

• 	Go to https://www.cloudflare.com

• 	Click Sign Up

• 	Enter your email and create a password

## Add Your Domain to Cloudflare

• 	After logging in, click Add a Site

• 	Enter your purchased domain name (rajeshtravelmemory.online )

• 	Click Add Site

## Choose a Plan

• 	Select the Free plan (sufficient for most personal and small business sites)

• 	Click Continue

## Review DNS Records

• 	Cloudflare will scan your current DNS records from Namecheap

• 	Confirm or add necessary records:

• 	A Record:

• 	CNAME Record (for load balancer):


## Update Namecheap Nameservers

• 	Cloudflare will show two nameservers (dina.ns.cloudflare.com and mark.ns.cloudflare.com )

<img width="949" height="437" alt="Screenshot 2025-10-01 135304" src="https://github.com/user-attachments/assets/3022f176-4af8-4b1f-adea-f80474d2fd74" />


• 	Go to [Namecheap Dashboard → Domain List → Manage → Nameservers]

• 	Select Custom DNS

• 	Enter the two Cloudflare nameservers

• 	Click Save

## Wait for DNS Propagation

• 	It may take a few minutes to a few hours for DNS changes to propagate

• 	Cloudflare will notify you once your domain is active

<img width="953" height="533" alt="Screenshot 2025-10-01 135339" src="https://github.com/user-attachments/assets/439eceaf-2187-456e-80cb-f083b2f4bcf2" />


## Enable SSL and Performance Settings
• 	Go to SSL/TLS → Overview

• 	Set SSL mode to Full or Flexible

• 	Go to Speed → Optimization

• 	Enable Auto Minify and Brotli Compression

• 	Go to Caching → Configuration

• 	Set caching level to Standard



















