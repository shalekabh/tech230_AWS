# Cloud watch

Create an ec2 instance that runs the sparta app and make sure it runs:

Select the instance and scroll down and select the monitoring tab (or search cloudwatch in the search bar)

Select manage detailed monitoring:

![Alt text](pics_for_mds/manage%20detailed%20monitorig.png)


Check the enable detailed monitoring box and click confirm:


![Alt text](pics_for_mds/enable%20detailed%20monitoring.png)


Next click add to dashboard.

Click create new and name your dashboard and finally click add to dashboard:


![Alt text](pics_for_mds/new%20dashboard.png)


Then on the left hand menu select alarms the all alarms:

Create alarm:

### Set metrics

Choose select metric

In the search bar put your ec2 id in their then select ```EC2 > per-instance metrics```

Select the metric you want mine is CPU utilisation:


![Alt text](pics_for_mds/select%20metric.png)


Next you specify your metic condtions, keep the statistics to avarage and set the period to 1 minute:


![Alt text](pics_for_mds/specifiy%20metics%20conditions.png)


For theshold type, choose static and set the alarm to greater than your chose threshold percentage and choose next:


![Alt text](pics_for_mds/threshhold.png)


### Setting the notification

Under notification, choose in alarm, and select an SNS topic to notify when your alarm is triggered and click next:


![Alt text](pics_for_mds/alarm%20trigger.png)


Name and put a message in your alarm and click next:


![Alt text](pics_for_mds/message%20for%20alarm.png)


Create alarm and whne it is triggered you should get an email:

![Alt text](pics_for_mds/Screenshot%202023-05-25%20153326.png)