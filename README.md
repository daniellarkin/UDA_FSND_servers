
# TL;DR
I/P address 52.0.7.64; ssh port 2200; grader p/w: grader123


# Completed Actions
## General setup, user management & security
1.  Created Amazon Lightsail instance
2.  Updated package source lists and upgraded using apt-get
3.  Changed firewall access and closed port 22 and opened ports 80, 2200 & 123. I did this via the Lightsail control interface
4.  Changed the ssh login port from 22 to 2200
5.  Removed root ssh login access in the sshd_config
6.  Disabled password authentication in sshd_config, thus allowing only on keys
7.  Added "grader" user, password grader123
8.  Added "grader" user to the sudoers
9.  Used ssh-keygen to create public and private keys
10.  On the server, after switching to the grader user, I created .ssh directory and inside this the autohorized_keys file
11. Change permissions on the .ssh directory (700) and authorized_keys (644)
12. Switched back to the local account and verified ssh access for the grader user with keys using the following:
    ssh -i grader_rsa -p 2200 grader@52.0.7.64
    
## Application functionality
13. installed Apache
14. installed elinks text browser and verified that Apache was indeed serving data through localhost:80
15. Used the static IP on the Lighsail instance to verify the apache test page was also accessible publicly
16. Change /var/www/html/index.html to print Hello World
17. Installed apache wsgi and created test to print hello world. This was observed to work
18. Installed postgresql