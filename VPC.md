### Create a vpc

Search for VPC in the aws console:

![Alt text](pics_for_mds/vpc.png)

Click create vpc:

![Alt text](pics_for_mds/create%20vpc.png)

select VPC only, name it and set the ipv4(CIDR) to: ```10.0.0.0/16```:

![Alt text](pics_for_mds/select%20vpc%20name%20subnet.png)

Then create VPC.

Select internet gateway from the left menu and click create internet gateway:

![Alt text](pics_for_mds/create%20igw.png)

Name it and create it:

![Alt text](pics_for_mds/name%20create%20igw.png)

Find your IGW, select it, click the actions button and select attach to vpc:

![Alt text](pics_for_mds/attach%20igw%20to%20vpc.png)

Then find your VPC and attach it explicitly.

Next find subnets on the left menu and click create subnet:

![Alt text](pics_for_mds/create%20subnet.png)

Select your vpc and name your subnet:

![Alt text](pics_for_mds/select%20vpc%20name%20subnet.png)

Choose your AZ and the cidr block you want and click create subnet:

![Alt text](pics_for_mds/az%20cidr%20create.png)

Next select route tables from the left menu.

Create route table:

![Alt text](pics_for_mds/create%20route%20table.png)

Name it and create it:

![Alt text](pics_for_mds/name%20create%20rt.png)

Find and select your subnet, click actions then click edit subnet associations:

![Alt text](pics_for_mds/subnet%20ascotiation.png)

Select your subnet and save associations:

![Alt text](pics_for_mds/select%20vpc%20name%20subnet.png)

Find and select your route table again, click actions then this time select edit route:

![Alt text](pics_for_mds/edit%20route.png)

Then we click add route and set it so that the destination is ```0.0.0.0/0``` and you target is your internet gateway:

![Alt text](pics_for_mds/add%20route.png)

Lastly we set up an EC2 instance like normal until we get to network settings and the SG. Select edit. Then select your vpc and public subnet and select enable auto assign public ip:

![Alt text](pics_for_mds/network%20settings.png)

We have to create a new SG because its a new VPC, open ports 22, 80 and 3000:

![Alt text](pics_for_mds/network%20settings1.png)

![Alt text](pics_for_mds/network%20settings2.png)

![Alt text](pics_for_mds/network%20settings3.png)

Set your user data to install and run nginx in advanced details then create the EC2:

```
#!/bin/bash

sudo apt-get update -y
sudo apt-get upgrade -y
sudo apt install nginx -y
sudo systemctl start nginx
sudo systemctl enable nginx
```

Select your EC2 instance once its finished setting up and copy and paste the public IP into the url using HTTP:
![Alt text](pics_for_mds/welcome%20to%20nginx.png)