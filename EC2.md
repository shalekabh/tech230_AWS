# Setting up an ec2 instance

Once you are logged in, in the top right hand corner, change your location to eu-west-1 Europe(reland):

![Alt text](pics_for_mds/ireland.png)

Then in the search bar, type ec2 and select it from the drop down menu:

![Alt text](pics_for_mds/ec2.png)

You should see this:

![Alt text](pics_for_mds/resouces%20page.png)

Next scroll down to launch instance and from the drop down menu, choose launch instance:

![Alt text](pics_for_mds/launch%20instance.png)

Make a name for your instance and follow the naming convention:

![Alt text](pics_for_mds/name%20ec2.png)

Select your AMI:

![Alt text](pics_for_mds/ami.png)

Choose the version:

![Alt text](pics_for_mds/ubuntu%20version.png)

Keep the instance type the same:

![Alt text](pics_for_mds/instance%20type.png)

Select your key pair:

![Alt text](pics_for_mds/aws%20key.png)

Select "edit" in network settings:

![Alt text](pics_for_mds/aws%20net%20edit.png)

Scroll down to firewarll security groups and create a new security group:

![Alt text](pics_for_mds/sgnamedesc.png)

Set the name ans keep the SG rules the same

![Alt text](pics_for_mds/sg%20rules.png)

Scroll down to summary section and launch instance:

![Alt text](pics_for_mds/sumlaunch.png)

It should say success, then click the inctance id number to take us to our instances page:

![Alt text](pics_for_mds/success.png)

It should look like this:

![Alt text](pics_for_mds/statuscheck.png)

When checks are passed it should look like this:

![Alt text](pics_for_mds/statuspass.png)

Next we click the instance id again on the actual instance this time and it will take us to this page:

![Alt text](pics_for_mds/ec2%20connect.png)

We click connect and it takes us to this page:

![Alt text](pics_for_mds/sshclient.png)

Select the ssh section and follow the steps.

Launch a gitbash and ```cd``` to .ssh and ```ls``` to see the files:

![Alt text](pics_for_mds/cdsshls.png)

Give yourself permission for the key:

![Alt text](pics_for_mds/permissionsssh.png)

Then copy the code from here and enter it into your terminal:

![Alt text](pics_for_mds/sshclient2.png)

It should ask to keep your fingerprint, when prompted say yes and it should look like this:

![Alt text](pics_for_mds/fingerprint.png)

Then update and upgrade using :

```sudo apt update -y``` and ```sudo apt upgrade - y```

Then install, start and enable nginx:

```sudo apt install nginx -y```, ```sudo systemctl start nginx``` and ```sudo systemctl enable nginx```

Go back to you instance, copy and paste the IP into the URL and it should bring up the nginx home page!

Congratulations!