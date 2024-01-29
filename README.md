IAM:-
Policy
1. Create a policy to access all objects in a specific bucket.
Ans-create s3 full permission policy and add specific bucket arn
2. Create a policy to access only 2 objects in a specific bucket.
Ans;-create policy to read and list and resources arn specific bucket 
3. Create a policy to deny the access of Specific bucket.
Ans-create a policy permission apply for deny and use specific bucket arn or apply
4. Create policy to create the user only and can attach policy to them.
Ans;-create user→access level→write-create user→attach 
5. Create a policy to place the user in a group only.
Ans;-create policy→access level→write-user in group –create 
6. Policy to get "read" access of all users, groups but not policy.
Ans;-create role and attach read only 
7. Policy to get access to billing, ec2 and cloudwatch.
Ans;-create policy biling→all action→add more permission →ec2→all action→add more permission—>cloudwatch→ all manual action →attach user policy


8. How to give access only to northern virginia.
Add 4 users >> 2 groups (devops & cloud) >> cloud member will access their password will only
no & devops group there no will password standards >> cloud group S3 full access % other EC2 full access >> Devops EC2 full access in north virginia.
Ans;-
Step1.create 4 iam user ;-krishna ,digambar ,akash,vrushabh
Step2.create 2 group;- cloud ,devops
Step3.assign members of group ;-1.cloud ;-krishna ,digambar 2.devops;-akash ,vrushabh
Step4.define policy in group;-1.cloud;-attaach   password
                                              2.decops;-
Step5;-define access permission;-1.cloud group;-access s3 and ec2 full
                                                      2.devops group;-ec2 full access in north virginia
9. Create a policy like when users are login into console, Without MFA not a single IAM user 
has able to access any AWS kind of aws services, he gots an permission denied error.
ans;-
10. Create a resource based policy and attach to S3_B16 Bucket & only sunny user can able to access that bucket.	
ans;-1. Create an IAM Policy for S3 Access , create the ploicy to the sunny user.
     2. attach the policy to the S3 bucket and  try to get access to the sunny user.
11.
user;-
1. Add four different users in the organisation account.
ans;-1. create an IAM User, and not attach any policy to that user.
     2. sign through the console and check the specific permission.
2. Add one user without permission.
Ans;-iam→user→create user→i want to create iam user–consol password-next-create user 
3. Add user with console & programmatic user.
ans;1.--iam→user→create user→provide console click here →i want to create iam user–consol password-next-create user 
2. create access key →command line access→next→aws configur

4. If IAM users are created w/o password, then how can you set the password of that IAM user as an Admin. (W/O deleting user)
Ans;-create user→name→next→create , goto user security credential→manage consol access
5. Add User Without Any permission (permission denied)
Ans;- create user ->name→create
6. S3 Read Only Access
Ans;-useradd policy s3 read only 
7. Jarvis Admin Access
Ans;-useradd admin policy 
8. Add User with Programmatic Access
Ans;- create user and get ssh→


S3:-
1.Implement MFA on Bucket when users are going to delete any objects, then he needs an Approval from MFA Code.
        Ans:- 
2.Create a Bucket with cli commands & upload the object from cli mode.
Ans;- step 1 .aws s3 create-bucket —>bucket-bucket-name
         Step 2.aws s3 cp filename s3:// bucket name
        Check it-  Aws s3 ls
3.Complete one project with server less static website hosting, with deployment & after deployment management of the website in backend side. Make a proper document of that project.
-Ans;-  steps -create 1 bucket→ insert object in css template with extract file
→Make bucket public,and object public→Server access logging enable and choice to bucket→Server website hosting -index.html ,error.html→Aws cloud trail create→cloudTail-name-storage location in bucket—>Addition setting - sns notification enable→Next→Event type all selected→Data event s3 select→Insight event all→Go to sns service→Topic-open cloud trail→Create subcribtiion→Protocol email→Endpoint email id→Create subscription →Go to email and confirm subscription




AWS Cloud Trail:-
1.Configure and enable the trail for multi region in your both staging and production account.
ans;-create a trail→ trail name :- production trail→choose option use exiting s3 bucket (for store s3 logs)-->trail log bucket name : choose bucket→prefix - optional→log file sse-kms encryption - enabled→aws kms alias→additional details - by default
–> clodwatch logs - by default→ tags - by default→next→ choose log events - management events→ management events - by default→ create trail

review trail and ensure this trail is enable for multi reason or not and repeat this  for staging account only change name of the trail

2. Configure and enable the trail for the only hyderabad region in your both staging and production account.
ans;-create a trail
2)  trail name :- production trail →  choose option use exiting s3 bucket (for store s3 logs)-->trail log bucket name : choose bucket→prefix - optional→ log file sse-kms encryption - enabled→ aws kms alias→  additional details - by default→cloudwatch logs - by default→ tags - by default→ next→choose log events - management events→management events - by default→ create trail

 repeat this process for staging account only change name of the trail and enable trail for hyderabad region you click on newly created trail on go to right corner setting and enable multi region you automatically go to specific reason



3.Create a trail for one service S3 by default it enables all logging features, you guys disable some features of logging.
Ans;-step;-1> cloudtrail→trail name→storage location→Trail log bucket name—>Log file SSE-KMS encryption—→Additional settings→next
            Step ;-2> event type-all→api activity→read,write→data event→s3-log all event→create cloudtrail

AWS SNS:-
1.Configure SNS with s3 static website.

ans;-Create the bucket and upload the object 
     2. Make the bucket public, enable the ACL→ Static web site hosting enable
     3. make the Object public, and hit the web site by get the link from static website.
     4. go to setting in the event section elect the SNS topic which is subscribe through
 the gmail of our account
        to get the notification of the event upload in the bucket, delete the object in the bucket through sns service   provide by aws.
      5. select the event type of s3 object perform in the bucket.
      6. Choose the destination where the message is going to be send.



2.Configure SNS with Email server level notification with Load Balancer configuration .
ans;-Step 1];-create topic→standard→name→display-name→create topic
Step 2];-create subscription→select topic arn→protocol→email→endpoint–email→ →create
Step 3];-email open and subscribe
 

           3.Configure the SNS with SMS level.
Ans; -
Step 1];-create topic→standard→name→display-name→create topic
Step 2];-create subscription→select topic arn→protocol→sms→endpoint–add mobile no→create 

Ec2;-

Create an Application Load Balancer with mobile, laptop, tablet, clothes, shoes pages?
          ans;-step1;- create first server;-
1-->home create 2 server
#!/bin/bash
sudo -i
apt install nginx -y
systemctl start nginx 
systemctl enable nginx
systemctl status nginx
echo "hi krishna this is homepage$HOSTNAME" > /var/www/html/index.html

2-->tshirt create 2 server
#!/bin/bash
sudo -i
apt install nginx -y
mkdir -p /var/www/html/tshirt
systemctl start nginx 
systemctl enable nginx
systemctl status nginx
echo "hi krishna this is tshirt page$HOSTNAME" > /var/www/html/tshirt/index.html

3-->mobile create 2 server
#!/bin/bash
sudo -i
apt install nginx -y
mkdir -p /var/www/html/mobile
systemctl start nginx 
systemctl enable nginx
systemctl status nginx
echo "hi krishna this is mobilepage$HOSTNAME" > /var/www/html/mobile/index.html

4-->earphone create 2 server

#!/bin/bash
sudo -i
apt install nginx -y
mkdir -p /var/www/html/earphone
systemctl start nginx 
systemctl enable nginx
systemctl status nginx
echo "hi krishna this is earphone$HOSTNAME" > /var/www/html/earphone/index.html

---------------------------------------------------------------------------------------------------------------
target group;-
basic configuration ;- instance-->target group name-->port=http-80/tcp-->ip add=ipv4
-->vpc--default-->health check=default-->attributes-->default
next-->register target--->select instance ex-app-home-->include as pending below-->create
-----------------------------------------------------------------------------------------------------------------
create application load balancer;-
Load balancer name-->scheme=internet facing-->IP address type=ipv4-->Network mapping=vpc=default-->mapping- Availability Zones=all
security group=default-->Listeners and routing = https=80=default action =(select target group =ex-home)
------------------------------------------------------------------------------------------------------------------

your application load balancer open--> 1rule--> open--add rule-->name ex(tshirt)-->Define rule conditions--add condition-->Rule condition types ex(path)-select
= /tshirt/  --confirm--select rule by created--next-->Action types Routing actions=Forward to target groups---select target group= ex(tshirt)--next
Forward to target groups-Priority-100-->next--create
syntax;-add rule
EC2--Load balancers--applic--HTTP:80 listener--Add rule

Result;-loadbalancer dns hit—check it    1 default 2 /tshirt 3 mobile


Create a Simple Application Load Balancer with Auto scaling and host any free css template.
Ans;-
Prerequisites:
1. Lunch template
2. Load Balancer (DNS)
3. Hit (CLB)


steps1;=
Create lunch template→name→ami→keypair–advance details-user data
#!/bin/bash
sudo -i
sudo apt install nginx -y
sudo systemctl start nginx.service
sudo systemctl enable nginx.service
sudo apt install unzip -y
cd /var/www/html/
sudo curl -O https://www.free-css.com/assets/files/free-css-templates/download/page296/oxer.zip
sudo unzip oxer.zip
sudo systemctl restart nginx.service
sudo systemctl status nginx.service

create auto scaling group:=
step 1;=name auto scaling group ,select launch template ,next
step2;=network =vpc select, Availability Zones and subnets=select az, next
step3;=load balancer=default ,Health checks=enable ,Additional settings=monitoring=enable cloudwatch cpu utilization ,next 
step4;=Group size =group size=desired minimum=1 // Scaling= ,minimum=1 ,mzimum=3 ,next
step5;=add notification for sns;=create topics for=add email and subscribe ,next

 
2. Load balancer---->Classic Load Balancer - previous generation
load-balancer name -->vpc default select-->mapping--->Availability Zones /all--->security group-->defaults and instance selected to m/c
Listeners and routing --->https/80 port---->Health checks---https--80  path / or index.html
instance--add instance---attributes defaults

Result;-classic load balance dns hit 


Create a simple classic Load Balancer.
Ans;- Load balancer---->Classic Load Balancer - previous generation
load-balancer name -->vpc default select-->mapping--->Availability Zones /all--->security group-->defaults and instance selected to m/c
Listeners and routing --->https/80 port---->Health checks---https--80  path / or index.html
instance--add instance---attributes defaults


Create an AMI Image, with name(tomcat-ami-v1) from an existing running tomcat server.
Ans;-
Prerequisite;-
1.ec2-server
2.ami
Step1.create ec2 server—>name→ubuntu ami→keypair–sg→lunch
Step2.select lunch instances→image and template→create image→
name-tomcate-ami-v1–create ami
Host any customised HTML web page in Ubuntu server.
Ans;-
Prerequisite;-
1.ec2 server
2.keypair
3.ami image
4.security group-ssh ,http ,https


Ans;-  ec2- name- ami ubuntu-instance type-keypair-advanced details
#!/bin/bash
sudo -i
apt-get install nginx
systemctl start nginx
systemctl enable nginx
systemctl status nginx
 instance public ip hit
Result;-welcome nginx

Host any customised HTML web page in RedHat 9 server.
Ans;-
Prerequisite;-
1.ec2 server
2.keypair
3.ami image
4.security group-ssh ,http ,https
ans;-ec2- name- ami redhat 9-instance type-keypair-advanced details
#!/bin/bash
sudo -i
apt-get install nginx
systemctl start nginx
systemctl enable nginx
systemctl status nginx
 instance public ip hit
Result;-welcome nginx

Host any customised HTML web page in windows 11 server.
Ans;-prequisite;-
 
Create a one EC2 Instance with debian family, create an 1000 no of jarvis.txt files and mount the existing S3 bucket into the same server and do upload all the jarvis.txt files into s3 bucket using aws command line tool.
Prerequisite;-
1.ec2-server
2.ami ubuntu
3.keypair
4.security group

Ans;-step1> ec2→name-ubuntu→ubuntu-ami→keypair→sg→create
       step 2> ssh→ssh -i keypair→ ununtu@ ip
       Step3>  touch jarvis {1..1000}.txt→ ls
       step4> Mount Existing S3 Bucket→sudo mkdir /mnt/s3
        step5>uploading ->cd /mnt/s3
                ls



Do task number 1 in AWS EC2 in scripting. Automate the whole server level configuration.
Ans;-
Step;-ec2–name→ami image–ubuntu→keypair→sg-22,80,443→advance details→user data write script→
                    #!/bin/bash
                    Sudo -i
                    apt install nginx -y
                    systemctl start nginx.service
                    systemctl enable nginx.service
                    systemctl status nginx.service
                     Lunch instance—>
               Result;-get instance public ip go to google put ip→welcome to nginx
If your server lost the key-pair, and you wanna take a ssh of that server, then how can you recover the key and take a ssh. (Want the practical, with documentation)
Ans;-
Step1.that server select→action→image and template→create image—>name→create image
Step2.ami→ select→lunch instance from ami—>name→ami image→keypair—>sg-22,80,etc→lunch instance
Result;-get ssh new lunch server

AWS VPC:-
1.Create a 5 VPC with different networks.
Ans;- vpc only→vpc name
1.192.168.0.0/24 .2.172.53.0.0/24 3.10.0.0.0/24 4.172.31.0.0/24 5.12.0.0.0/16
2.Create a customised VPC and enable the DHCP & DNS option set.
Ans;-prerequisite;-
      1.vpc
      2.subnet
      3.dhcp optionset
      4.ec2-server
Step1.vpc
Create vpc→name→ipv4 cidr→10.0.0.0/16→create
Step2.subnet
Choose the vpc by created→availablity zone select→ipv4 subnet cidr→10.0.0.1/24→create
Step3.dhcp set 
Create dhcp set→name→domainname →cloudblitz.com
Step4.vpc edit
Vpc→edit vpc setting dhcp →choose the newly created dhcp set
Step5.ec2-server lunch
Lunch instance→name→ubuntu ami→keypair→network setting→vpc created by me→subnet→default—>lunch instance
Result;- select the instance and details check hostname type

3.Enable the flow logs of newly created custom VPC.
Ans;-
Prerequisite;-
1.bucket
2.vpc

           Ans;-step1.create bucket→name→create→copy arn
step2. vpc→name→ipv4-10.0.0.0/16–create
           Vpc–select-action→crate flow log→name–filter-all→Maximum aggregation interval-10min→destination→s3 bucket→arn bucket→create flow logs.

Create a Network Load Balancer (Need proper flow diagram, with explanation)
ans;-
Create a 3 VPC & do the peering between 3 VPC.
Prerequisite;-
1.vpc-3 from different network
2.igw-3
3.route table
4.transite getway












VPC's(N.V region)Create vpc1 - cidr 10.0.0.0/16
create subnet→ select vpc1→ AZ - 1a→ cidr - 10.0.1.0/24Create IG→ igw1
Rename route-1→ actions→ edit route table→ add route→ default→ igw1Attach igw1 to vpc-1
Create vpc2 - cidr 10.1.0.0/16create subnet→ select vpc2→ AZ - 1b→ cidr - 10.1.1.0/24
Create IG→ igw2
Rename route-2→ actions→ edit route table→ add route→ default→ igw
Attach igw2 to vpc-2Create 
Create vpc3 - cidr 10.2.0.0/16
create subnet→ select vpc2→ AZ - 1b→ cidr - 10.2.1.0/24
Create IG→ igw2
Rename route-2→ actions→ edit route table→ add route→ default→ igw3
Attach igw2 to vpc-3
Create Transit Gateway→ name→ description→ create
To attach TGW to vpc's we need to create separate Transit gateway attachments for each vpc
create TGW attachments→ name→ select created TGW id→ type - vpc→ vpc id→ create
Modify route tables→ route-1→ cidr of 2nd and 3rd vpc→ select Transit GW-1→ route-2→ cidr of 1st and 3rd vpc→ select Transit GW-2→ 				save
 route-3→ cidr of 1st and 2nd vpc→ select Transit GW-3→ 				save


Create instances→ instance-1→ select vpc1→ public ip enable→ launch→ SG→ allow custom icmp→
 launch   instance-2→ select vpc2→ public ip enable→ launch→ SG→ allow custom icmp→ launc
 instance-3→ select vpc3→ public ip enable→ launch→ SG→ allow custom icmp→ launch


Ssh and ping each other’s ip address



Ssh and ping each other’s ip addr



Access the all S3 Buckets in Particular single customised VPC w/o internet, so how can we achieve it ?
Ans;-
Prerequisite;-
1.vpc 
2.subnet
3.igw
4.route table
5.server

Create vpc→ myvpc→ 172..53.0.0/16  —256ips
Create subnet→ subnet-pub→ 1a→ subnet cidr - 172.0..1/28 —-------- 16ips
		     subnet-priv→ 1b→ subnet cidr - 172.53.0.65/26 —----- 16ips
Create IGW→ attach to vpc
	           Default route→edit route–destination-0.0.0.0/0-target-internet getway-select igw→ attach igw
Create route→ name - NAT-RT→ select vpc→ create
                        Edit route-destination-0.0.0.0/0-target-internet getway-select igw→ save
Create instance→ instance-1→ select vpc→ subnet - pub→ public ip - enable→ launch
		        instance-2→ select vpc→ subnet - priv→ public ip - disable→ launch
Create NAT gw→ name→ subnet-pub→ allocate elastic ip→ create
Edit private route - NAT-RT→ add route→ 0.0.0.0/0 - NAT gw
Ssh public server→ vim keyname→ copy the all key content and paste → chmod 400 key→ ssh private server→ ping 8.8.8.8
Edit private route→ Edit subnet association - subnet-priv→ save
Edit private route - NAT-RT→ disassociate private-subnet
IAM service→ create role s3FullAccess→ attach role to private instance
Create Endpoint→ select services→ search s3(us.east.1) - type gateway→ select vpc→ select default route→ create

Result:- aws s3 ls —----- aws not found→curl -O url→ls→sudo apt install unzip→unzip file→cd aws →sudo ./install→ aws s3 ls 


