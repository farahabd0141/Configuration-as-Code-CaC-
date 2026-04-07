# Configuration-as-Code-CaC-


INET4031 Puppet Lab 9 – Configuration as Code
Program Description

In this lab, I used Puppet to automate setting up a system instead of doing everything manually. Normally, I would have to install stuff like Apache, PHP, and MariaDB one by one, and also create users using a bunch of commands in the terminal. That takes time and it’s easy to mess up.

With Puppet, I just write everything in a file and run one command, and it does everything for me. It installs packages, starts services, and creates users automatically. This makes it way easier and faster.

Program User Operation

There are two main things in this project:

creating users and groups
setting up the LAMP stack

Everything is done using Puppet files.

Input File Format

The input file is used to create users. Each line looks like this:

username:password:last:first:groups

Example:

user05:pass05:Last05:First05:group02
user06:pass06:Last06:First06:group01,group02

What each part means:

username = login name
password = password
last = last name
first = first name
groups = what groups the user is in

If you don’t want the user in a group, just put -
If you want multiple groups, use commas
If you want to skip a line, put # in front

Command Execution

First go to the folder:

cd ~/abdi_inet4031_puppet_lab9

Run the user setup:

sudo puppet apply server_users_groups.pp

Then run the LAMP setup:

sudo puppet apply lamp_stack_server.pp
What the files do

server_users_groups.pp

creates users
sets passwords
adds them to groups

lamp_stack_server.pp

installs apache
installs php
installs mariadb
starts and enables services

phpinfo.php

used to test if php is working
Testing

After running everything, go to:

http://<your-ip>/phpinfo.php

If it works, you’ll see a PHP page with a bunch of info.

Why this matters

This lab shows how automation works. Instead of doing everything manually every time, you can just run Puppet and it sets everything up the same way every time.

This is important in real jobs because it saves time and avoids mistakes.

Notes
use sudo when running commands
if something doesn’t work, just run puppet again
make sure your files don’t have errors
