 SSH Server Not Listening on the Correct Port
Ensure SSH is listening on the correct port (55555). If SSH is not configured to listen on port 55555, UFW might allow the traffic, but the server will not respond.

Check the SSH configuration by opening the SSH configuration file:

```
sudo nano /etc/ssh/sshd_config

```
Look for the Port directive and ensure it includes 55555. It should look like this:

```
Port 22
Port 55555

```
After making any changes, restart the SSH service:

```
sudo systemctl restart ssh

```
Now, verify that SSH is listening on port 55555 by running:


```
sudo ss -tuln | grep 55555

```
You should see output similar to:

```
LISTEN   0         128               *:55555             *:*

``