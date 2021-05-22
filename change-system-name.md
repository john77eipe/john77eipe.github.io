## Changing system name

During the installation we provide our system a name. We come across this system name every time we use a shell. (Usually a shell prompt displays user name and system name) To change this we need to make modification to 2 files – hostname file and hosts file.

Example:
On my system, the shell prompt is displayed as

```sh
eipe@eipe-john:~$
```
to change my current system name “eipe-john” to anything else say, “eipe-system”
follow the these steps:
#### Step 1:
Open terminal
type
```sh
sudo vi /etc/hostname
```
When prompted, enter the administrator password.
The hostname file will open, displaying the current computer name. Replace the current computer name with the desired new name.
Save and exit.
#### Step 2:
Next type
```sh
sudo vi /etc/hosts
```
The hosts file will open, displaying a mapping of IP addresses to DNS names.
This file is used by the system to map some of the host names to IP addresses before a DNS server can be referenced. In the absence of a name server, any network program on your system consults this file to determine the IP address that corresponds to a host name.
```sh
127.0.0.1 localhost.localdomain localhost ::1 eipe-system localhost6.localdomain6 localhost6 
127.0.1.1 eipe-system
```
The leftmost column is the IP address to be resolved. The next column is that host's name. Any subsequent columns are alias for that host.
After making the changes, restart the system.