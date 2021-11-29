# DevOps Intro
DevOps is a set of practices intended to reduce the time between comitting a change to a system and the change being placed into normal production while ensuring high production.

**DevOps principles**
- Customer-Centric Action
- End-To-End Responsibility
- Continuos Improvement
- Automate Everything
- Work as one team
- Monitor and test everything



## Development Env

- Install vagrant
- Install Ruby


**Linux commands**
- `sudo apt-get update -y`
```
# creating a virtual machine with Linux Ubuntu 16.04
# ubuntu/xenial64

Vagrant.configure("2") do |config|

 # choose the os/box/distro
 config.vm.box = "ubuntu/xenial64"
 config.vm.network "private_network", ip: "192.168.10.100"  
# vagrant destroy
# vagrant up
# vagrant reload
end
```
- Who am I `uname -a`
- Where am I `pwd`
- list dir or all `ls` or `ls -a`
- copy file `cp filename destination`
- cut or rename `mv filename destination`
- create file `touch filename`
- create folder `mkdir foldername`
- how to navigate `cd foldername` retrun step back `cd ..`
- deleting file folders `rm -rf namefolder`

> Task: Create a folder called test, create a file called text.txt inside the test folder then copy the text.txt to your home location `/home/vagrant`

**File Permissions**
- Read `r`, Write `w` and `x`
- how to check permissions `ll`
- change permision `chmod permision filename`

- find out all processes running `top`
- how to `kill` a process 

### Automate everything we have done manually
- provision the steps of updating, upgrading and nginx installation
  
> vagrant up again
- `vagrant status` to see if vagrant is running
- `vagrant ssh` to open a vm
- `touch provision.sh` to create an sh file
- `nano provision.sh` to edit provision file and add the following comands:
```
#!/bin/bash

sudo apt-get update -y
sudo apt-get upgrade -y
sudo apt-get install nginx -y

```
- save and close provision.sh
- make provission.sh executable by:
- `sudo chmod +x provision.sh`
- run sh file by `./provision.sh`
- now you are able to launch nginx on your browser 

### Pipes and Filters

A pipe can pass the standard output of one operation to the standard input of another, but a filter can modify the stream. A filter takes the standard input, does something useful with it, and then returns it as a standard output. Linux has a large number of filters. Some useful ones are the commands awk, grep, sed, spell, and wc.

**Display first 2 lines in a file**
`cat <filename> | head -2`

**Display last 2 lines in file**
`cat <filename> | tail -2`


