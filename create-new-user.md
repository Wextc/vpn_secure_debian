1. Create a new user
First, log in to your server as the root user or a user with sudo privileges.

Use the following command to create a new user (replace newuser with the desired username):

bash
Copy


sudo adduser newuser




This command will prompt you to set a password for the new user and optionally provide additional information like Full Name, Room Number, etc. You can leave these fields blank and press Enter to skip.

2. Add the new user to the sudo group
To grant the new user sudo privileges, add them to the sudo group:

bash
Copy
sudo usermod -aG sudo newuser
The -aG flag adds the user to the sudo group without removing them from any other groups.

3. Verify sudo access
You can now switch to the new user and verify that they have sudo privileges.

Log in as the new user:

bash
Copy
su - newuser
Then, run a command with sudo, like checking the system date:

bash
Copy
sudo date
The first time you run a sudo command, the user will be asked to enter their password. If everything is configured correctly, the command will run with sudo privileges.

4. (Optional) Check if sudo is working properly
If you want to confirm the user has been added to the sudo group, you can check with:

bash
Copy
groups newuser
You should see sudo listed among the groups for the user.

That's it! The new user should now have sudo privileges on your Debian server.