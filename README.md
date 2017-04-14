# AWS-Ubuntu
Config Server on Local VM box

### ERROR = ssh: connect to host 192.168.1.7 port 22: Connection refused
```
sudo service ssh status /  sudo service ssh start
```
### ERROR = SSH Refusing Connection

```
sudo apt-get update
sudo apt-get install openssh-server
```

#### Initial Server Setup with Ubuntu 16.04

```
//Step One — Root Login
$ssh root@your_server_ip

//Step Two — Create a New User
$ adduser jeeten

//Step Three — Root Privileges
$ usermod -aG sudo jeeten

//Step Four — Add Public Key Authentication (Recommended)
$ ssh-keygen
$ ls
$ cat ~/.ssh/id_rsa.pub  #id_rsa replace your key name
```

####On the server, as the root user, enter the following command to temporarily switch to the new user (substitute your own user name):
```
su - sammy
Now you will be in your new user's home directory.

Create a new directory called .ssh and restrict its permissions with the following commands:

mkdir ~/.ssh
chmod 700 ~/.ssh
Now open a file in .ssh called authorized_keys with a text editor. We will use nano to edit the file:

nano ~/.ssh/authorized_keys
Now insert your public key (which should be in your clipboard) by pasting it into the editor.

Hit CTRL-x to exit the file, then y to save the changes that you made, then ENTER to confirm the file name.

Now restrict the permissions of the authorized_keys file with this command:

chmod 600 ~/.ssh/authorized_keys
Type this command once to return to the root user:

exit
```
