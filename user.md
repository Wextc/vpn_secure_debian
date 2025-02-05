- Use the following command to create a new user (replace newuser with the desired username):



```
sudo adduser newuser


```
Check what user is logged in:



```
whoami


```


Check if the admin user has sudo privileges:

- You can confirm if your admin user(you created that user) has the ability to run commands as root by checking if they are in the sudo group. Run:


```

getent group sudo

"If your admin user is listed here, it means they have sudo privileges.


```


- To switch to another user from the command line, you can use the su (substitute user) command or sudo depending on your system and privileges. Here's how:


```
su - username

# Or You  sudo (Super User Do): If your user has sudo privileges, you can run:

sudo -u username - i # This will execute an interactive shell (-i) as the specified user (username).



```

In both cases, after executing the command, you'll be in the other user's shell and can execute commands as that user.




## To reconnect to vps using the new user.


Simply use:

```
ssh admin@your_vps_ip

```

