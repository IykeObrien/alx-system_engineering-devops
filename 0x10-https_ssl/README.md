HTTPS SSL


SSL stands for Secure Sockets Layer and, in short, it's the standard technology for keeping an internet connection secure and safeguarding any sensitive data that is being sent between two systems, preventing criminals from reading and modifying any information transferred, including potential personal details. The two systems can be a server and a client (for example, a shopping website and browser) or server to server (for example, an application with personal identifiable information or with payroll information).

HTTPS (Hyper Text Transfer Protocol Secure) appears in the URL when a website is secured by an SSL certificate. The details of the certificate, including the issuing authority and the corporate name of the website owner, can be viewed by clicking on the lock symbol on the browser bar.

What happens when you don’t secure your website traffic? 

Prerequisites
What is HTTPS?
What are the 2 main elements that SSL is providing
HAProxy SSL termination on Ubuntu16.04
SSL termination
Bash function
Tasks ✔️
0-world wide web
1-haproxy ssl termination
100-redirecthttp to https
Requirements
Allowed editors: vi, vim, emacs
All your files will be interpreted on Ubuntu 16.04 LTS
All your files should end with a new line
A README.md file, at the root of the folder of the project, is mandatory
All your Bash script files must be executable
Your Bash script must pass Shellcheck (version 0.3.7) without any error
The first line of all your Bash scripts should be exactly #!/usr/bin/env bash
The second line of all your Bash scripts should be a comment explaining what is the script doing
Installing SSL Termination on Haproxy
Linux Distro: Ubuntu 20.04 LTS
HAProxy Version: v2.4.3
#if you already have haproxy installed do this
$ sudo snap install --classic certbot

# check if haproxy is installed, if yes stop haproxy
$ sudo service haproxy stop

# Install ssl using certbot
$ sudo certbot certonly --standalone

# Follow the instrustions accurately, at the end please take note of the
# Location of your SSL Keys. Usually going to default to the /etc/letsencrypt
# directory. To view them do the below
$ ls /etc/letsencrypt/live/domain name/

# Now concat your certificate .pem files to a single pem file and save them to
# /etc/ssl/private
$ cat cert key 1 cert key 2 > /etc/ssl/private/any desired name.pem

# Now go to your haproxy config file to add a the path to your certificate
# Then reload haproxy
$ sudo service haproxy reload
If you don't have HAProxy installed just copy and run this on your terminal and save yourself the hassle

$ wget -O haproxy https://github.com/sammykingx/alx-system engineering-devops/raw/master/0x0F-load balancer/install haproxy safely &&
