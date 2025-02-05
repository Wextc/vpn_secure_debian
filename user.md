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

 to give the admin user sudo privileges:
Option 1: Adding the admin user to the sudo group (recommended)
Login as root or a user with sudo privileges: If you're logged in as root, you can skip to the next step. If you're logged in as another user with sudo privileges, use sudo to make the changes.

Add the admin user to the sudo group: Run the following command:

```
sudo usermod -aG sudo admin

```
This will add the admin user to the sudo group, which automatically grants sudo privileges (this is the preferred method).

Verify the user has been added to the sudo group: Run this command to verify:


```
groups admin

```
You should see sudo listed among the groups for the admin user.

Logout and log back in: To apply the changes, log out and then log back in as the admin user. You should now be able to use sudo with the admin account.

Option 2: Manually editing the sudoers file (if necessary)
Login as root or use an existing sudo user: As before, you'll need to log in as a user with administrative privileges.

Edit the sudoers file: Open the sudoers file using visudo (which safely edits the sudoers file and checks for syntax errors):

```
sudo visudo

```
Add the admin user with sudo privileges: Look for a line like:

```
root    ALL=(ALL:ALL) ALL

```
And below it, add the following line to grant admin the same privileges:

```
admin   ALL=(ALL:ALL) ALL

```
Save and exit: In visudo, after making the changes, press Ctrl+X, then press Y to confirm saving, and press Enter to exit.

Verify the admin user has sudo privileges: Now, log out and log back in as the admin user. You should be able to run commands with sudo.