### Connecting the posts page to the app:

First on your terminal that has mongodb, enter the config:

```sudo nano /etc/mongod.conf```

change the bind ip to ```0.0.0.0```

Save and exit

```Crtl + x```
```y```
```Enter```

Next go to the app terminal.

Open the environment variable file using:

```sudo nano .bashrc```

add ```DB_HOST=mongodb://<database ip>:27017/posts``` to the very bottom of the file

Save and exit:

```Ctrl + x```
```y```
```Enter```

Run: ```source .bashrc``` To restart it 

Then type ```printenv``` to check it saved:

Now manually install the dependecies in the AMI.md file if you didnt do it before.

Make sure you are in your app terminal and directory.

Restart and enable nginx:

```sudo systemctl restart nginx``` and ```sudo systemctl enable nginx```

Next go to your security group on AWS and set a rule to allow access to port 21017 from 0.0.0.0 - this is so our app can access the database server.

go back to app terminal seed and clear the database and start the app using:

```npm install```, ```node seeds/seed.js``` and ```pm2 start app.js --update-env```

Hopefully you should be able to access the posts page extenstion.