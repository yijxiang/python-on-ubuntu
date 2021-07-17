# 如何在ubuntu 20.04 系统中安装最新的python3

## ubuntu APT方法安装系统自带Python

先升级，再检查python3版本，2010.07 系统更新之后，python3 版本为3.8.10

- sudo apt update

```
sudo apt update
Hit:1 http://archive.ubuntu.com/ubuntu focal InRelease                                                                                        
Get:2 https://download.docker.com/linux/ubuntu focal InRelease [52.1 kB]                                                                      
Hit:3 https://artifacts.elastic.co/packages/7.x/apt stable InRelease            
Get:4 http://archive.ubuntu.com/ubuntu focal-updates InRelease [114 kB]         
Get:5 http://archive.ubuntu.com/ubuntu focal-backports InRelease [101 kB]
Get:6 http://archive.ubuntu.com/ubuntu focal-security InRelease [114 kB]                                                                            
Get:7 http://archive.ubuntu.com/ubuntu focal-updates/main amd64 Packages [1,086 kB]                                                                 
Get:8 http://archive.ubuntu.com/ubuntu focal-updates/main amd64 c-n-f Metadata [13.7 kB]                                                            
Get:9 http://archive.ubuntu.com/ubuntu focal-updates/universe amd64 Packages [841 kB]                                                               
Get:10 http://archive.ubuntu.com/ubuntu focal-updates/universe Translation-en [176 kB]                                                              
Get:11 http://archive.ubuntu.com/ubuntu focal-updates/universe amd64 c-n-f Metadata [18.4 kB]                                                       
Get:12 http://archive.ubuntu.com/ubuntu focal-security/main amd64 Packages [745 kB]                                                                 
Get:13 http://archive.ubuntu.com/ubuntu focal-security/main amd64 c-n-f Metadata [8,028 B]                                                          
Get:14 http://archive.ubuntu.com/ubuntu focal-security/universe amd64 Packages [632 kB]                                                             
Get:15 http://archive.ubuntu.com/ubuntu focal-security/universe Translation-en [97.2 kB]                                                            
Get:16 http://archive.ubuntu.com/ubuntu focal-security/universe amd64 c-n-f Metadata [11.9 kB]                                                      
Fetched 4,009 kB in 38s (107 kB/s)                                                                                                                  
Reading package lists... Done
Building dependency tree       
Reading state information... Done
2 packages can be upgraded. Run 'apt list --upgradable' to see them.

```

- sudo apt-get -y upgrade


```
sudo apt-get -y upgrade --fix-missing
Reading package lists... Done
Building dependency tree       
Reading state information... Done
Calculating upgrade... Done
The following packages were automatically installed and are no longer required:
  bridge-utils dns-root-data dnsmasq-base libevent-core-2.1-7 libevent-pthreads-2.1-7 libidn11 libopts25 sntp ubuntu-fan
Use 'sudo apt autoremove' to remove them.
The following packages will be upgraded:
  python3-distupgrade ubuntu-release-upgrader-core
2 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.
Need to get 23.9 kB/128 kB of archives.
After this operation, 1,024 B of additional disk space will be used.
Get:1 http://archive.ubuntu.com/ubuntu focal-updates/main amd64 ubuntu-release-upgrader-core all 1:20.04.35 [23.9 kB]                               
Fetched 23.9 kB in 12s (1,933 B/s)                                                                                                                  
(Reading database ... 196097 files and directories currently installed.)
Preparing to unpack .../ubuntu-release-upgrader-core_1%3a20.04.35_all.deb ...
Unpacking ubuntu-release-upgrader-core (1:20.04.35) over (1:20.04.33) ...
Preparing to unpack .../python3-distupgrade_1%3a20.04.35_all.deb ...
Unpacking python3-distupgrade (1:20.04.35) over (1:20.04.33) ...
Setting up python3-distupgrade (1:20.04.35) ...
Setting up ubuntu-release-upgrader-core (1:20.04.35) ...
Processing triggers for man-db (2.9.1-1) ...
```

- python3 -V

```
python3 -V
Python 3.8.10
```

- sudo apt-get install -y python3-pip
安装PIP3

- sudo apt-get install build-essential libssl-dev libffi-dev python3-dev
安装开发环境包


##### 资源清单

[How To Install Python 3 and Set Up a Programming Environment on an Ubuntu 20.04 Server](https://www.digitalocean.com/community/tutorials/how-to-install-python-3-and-set-up-a-programming-environment-on-an-ubuntu-20-04-server)


