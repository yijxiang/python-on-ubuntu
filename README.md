# 如何在ubuntu 20.04 系统中安装Python

## ubuntu APT方法安装系统自带Python

升级系统之后，再进行检查Python3版本，2010.07 系统更新之后，python3 版本为3.8.10

- sudo apt update   系统升级检查

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

- sudo apt-get -y upgrade    系统升级命令


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

- python3 -V  检查Python3 版本：

```
python3 -V
Python 3.8.10
```

- sudo apt-get install -y python3-pip
安装PIP3 包管理组件

- sudo apt-get install build-essential libssl-dev libffi-dev python3-dev
安装Python开发环境包

以上为安装和升级系统自带的Python方法，升级完成之后，可以看到ubuntu 20.04自带的Python3 版本为3.8.10。


## 安装最新的Python 3.9

如何在ubuntu 20上安装Python 3.9.x系统呢？
安装完成如果计划使用3.9.x，则命令不同，python3.9，系统自带的版本还是3.8的（可以通过命令：python3 得到）。

```
sudo apt-get install python3.9 --fix-missing
Reading package lists... Done
Building dependency tree       
Reading state information... Done
The following packages were automatically installed and are no longer required:
  bridge-utils dns-root-data dnsmasq-base libevent-core-2.1-7 libevent-pthreads-2.1-7 libidn11 libopts25 sntp ubuntu-fan
Use 'sudo apt autoremove' to remove them.
The following additional packages will be installed:
  libpython3.9-minimal libpython3.9-stdlib python3.9-minimal
Suggested packages:
  python3.9-venv python3.9-doc binfmt-support
The following NEW packages will be installed:
  libpython3.9-minimal libpython3.9-stdlib python3.9 python3.9-minimal
0 upgraded, 4 newly installed, 0 to remove and 0 not upgraded.
Need to get 4,977 kB of archives.
After this operation, 19.9 MB of additional disk space will be used.
Do you want to continue? [Y/n] Y
Get:1 http://archive.ubuntu.com/ubuntu focal-updates/universe amd64 libpython3.9-minimal amd64 3.9.5-3~20.04.1 [756 kB]
Get:2 http://archive.ubuntu.com/ubuntu focal-updates/universe amd64 python3.9-minimal amd64 3.9.5-3~20.04.1 [2,022 kB]                              
Get:3 http://archive.ubuntu.com/ubuntu focal-updates/universe amd64 libpython3.9-stdlib amd64 3.9.5-3~20.04.1 [1,776 kB]                            
Get:4 http://archive.ubuntu.com/ubuntu focal-updates/universe amd64 python3.9 amd64 3.9.5-3~20.04.1 [423 kB]                                        
Fetched 4,977 kB in 48s (104 kB/s)                                                                                                                  
Selecting previously unselected package libpython3.9-minimal:amd64.
(Reading database ... 196140 files and directories currently installed.)
Preparing to unpack .../libpython3.9-minimal_3.9.5-3~20.04.1_amd64.deb ...
Unpacking libpython3.9-minimal:amd64 (3.9.5-3~20.04.1) ...
Selecting previously unselected package python3.9-minimal.
Preparing to unpack .../python3.9-minimal_3.9.5-3~20.04.1_amd64.deb ...
Unpacking python3.9-minimal (3.9.5-3~20.04.1) ...
Selecting previously unselected package libpython3.9-stdlib:amd64.
Preparing to unpack .../libpython3.9-stdlib_3.9.5-3~20.04.1_amd64.deb ...
Unpacking libpython3.9-stdlib:amd64 (3.9.5-3~20.04.1) ...
Selecting previously unselected package python3.9.
Preparing to unpack .../python3.9_3.9.5-3~20.04.1_amd64.deb ...
Unpacking python3.9 (3.9.5-3~20.04.1) ...
Setting up libpython3.9-minimal:amd64 (3.9.5-3~20.04.1) ...
Setting up python3.9-minimal (3.9.5-3~20.04.1) ...
Setting up libpython3.9-stdlib:amd64 (3.9.5-3~20.04.1) ...
Setting up python3.9 (3.9.5-3~20.04.1) ...
Processing triggers for man-db (2.9.1-1) ...
Processing triggers for mime-support (3.64ubuntu1) ...
dnac@ubuntu20:~$ python3
Python 3.8.10 (default, Jun  2 2021, 10:49:15) 
[GCC 9.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 
dnac@ubuntu20:~$ python3.9
Python 3.9.5 (default, May 19 2021, 11:32:47) 
[GCC 9.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 
dnac@ubuntu20:~$ 
```

通过以上方法，可以在ubuntu 20中安装最新的Python 3.9.5的版本。


##### 资源清单

[How To Install Python 3 and Set Up a Programming Environment on an Ubuntu 20.04 Server](https://www.digitalocean.com/community/tutorials/how-to-install-python-3-and-set-up-a-programming-environment-on-an-ubuntu-20-04-server)


