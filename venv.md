### Python 虚拟环境设置 for 3.8

- sudo apt-get install -y python3-venv


```
sudo apt-get install -y python3-venv
Reading package lists... Done
Building dependency tree       
Reading state information... Done
The following packages were automatically installed and are no longer required:
  bridge-utils dns-root-data dnsmasq-base libevent-core-2.1-7 libevent-pthreads-2.1-7 libidn11 libopts25 sntp ubuntu-fan
Use 'sudo apt autoremove' to remove them.
The following additional packages will be installed:
  python3.8-venv
The following NEW packages will be installed:
  python3-venv python3.8-venv
0 upgraded, 2 newly installed, 0 to remove and 0 not upgraded.
Need to get 6,684 B of archives.
After this operation, 38.9 kB of additional disk space will be used.
0% [Working]
Get:1 http://archive.ubuntu.com/ubuntu focal-updates/universe amd64 python3.8-venv amd64 3.8.10-0ubuntu1~20.04 [5,456 B]
Get:2 http://archive.ubuntu.com/ubuntu focal/universe amd64 python3-venv amd64 3.8.2-0ubuntu2 [1,228 B]
Fetched 6,684 B in 17s (394 B/s)
Selecting previously unselected package python3.8-venv.
(Reading database ... 196131 files and directories currently installed.)
Preparing to unpack .../python3.8-venv_3.8.10-0ubuntu1~20.04_amd64.deb ...
Unpacking python3.8-venv (3.8.10-0ubuntu1~20.04) ...
Selecting previously unselected package python3-venv.
Preparing to unpack .../python3-venv_3.8.2-0ubuntu2_amd64.deb ...
Unpacking python3-venv (3.8.2-0ubuntu2) ...
Setting up python3.8-venv (3.8.10-0ubuntu1~20.04) ...
Setting up python3-venv (3.8.2-0ubuntu2) ...
Processing triggers for man-db (2.9.1-1) ...
```


-  python3 -m venv  venv

创建venv目录，python虚拟环境目录，最后的目录名称可以自定义

``` 
python3 -m venv  venv
ls venv
bin  include  lib  lib64  pyvenv.cfg  share

```

- 进入虚拟环境，查看初始package、python版本

```
source venv/bin/activate
(venv) dnac@ubuntu20:~$ 
(venv) dnac@ubuntu20:~$ 
(venv) dnac@ubuntu20:~$ python3
Python 3.8.10 (default, Jun  2 2021, 10:49:15) 
[GCC 9.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 
(venv) dnac@ubuntu20:~$ python
Python 3.8.10 (default, Jun  2 2021, 10:49:15) 
[GCC 9.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 
(venv) dnac@ubuntu20:~$ pip list
Package       Version
------------- -------
pip           20.0.2 
pkg-resources 0.0.0  
setuptools    44.0.0 
```

- deactivate 退出python虚拟环境

```
deactivate
dnac@ubuntu20:~/venv/bin$ 

```


### for 3.9

- 先安装 venv 模块： sudo  apt-get install python3.9-dev python3.9-venv

```
sudo  apt-get install python3.9-dev python3.9-venv
Reading package lists... Done
Building dependency tree       
Reading state information... Done
The following packages were automatically installed and are no longer required:
  bridge-utils dns-root-data dnsmasq-base libevent-core-2.1-7 libevent-pthreads-2.1-7 libidn11 libopts25 sntp ubuntu-fan
Use 'sudo apt autoremove' to remove them.
The following additional packages will be installed:
  libpython3.9 libpython3.9-dev
The following NEW packages will be installed:
  libpython3.9 libpython3.9-dev python3.9-dev python3.9-venv
0 upgraded, 4 newly installed, 0 to remove and 0 not upgraded.
Need to get 6,353 kB of archives.
After this operation, 27.3 MB of additional disk space will be used.
Do you want to continue? [Y/n] Y
Get:1 http://archive.ubuntu.com/ubuntu focal-updates/universe amd64 libpython3.9 amd64 3.9.5-3~20.04.1 [1,713 kB]
Get:2 http://archive.ubuntu.com/ubuntu focal-updates/universe amd64 libpython3.9-dev amd64 3.9.5-3~20.04.1 [4,124 kB]                               
Get:3 http://archive.ubuntu.com/ubuntu focal-updates/universe amd64 python3.9-dev amd64 3.9.5-3~20.04.1 [511 kB]                                    
Get:4 http://archive.ubuntu.com/ubuntu focal-updates/universe amd64 python3.9-venv amd64 3.9.5-3~20.04.1 [5,444 B]                                  
Fetched 6,353 kB in 52s (121 kB/s)                                                                                                                  
Selecting previously unselected package libpython3.9:amd64.
(Reading database ... 196776 files and directories currently installed.)
Preparing to unpack .../libpython3.9_3.9.5-3~20.04.1_amd64.deb ...
Unpacking libpython3.9:amd64 (3.9.5-3~20.04.1) ...
Selecting previously unselected package libpython3.9-dev:amd64.
Preparing to unpack .../libpython3.9-dev_3.9.5-3~20.04.1_amd64.deb ...
Unpacking libpython3.9-dev:amd64 (3.9.5-3~20.04.1) ...
Selecting previously unselected package python3.9-dev.
Preparing to unpack .../python3.9-dev_3.9.5-3~20.04.1_amd64.deb ...
Unpacking python3.9-dev (3.9.5-3~20.04.1) ...
Selecting previously unselected package python3.9-venv.
Preparing to unpack .../python3.9-venv_3.9.5-3~20.04.1_amd64.deb ...
Unpacking python3.9-venv (3.9.5-3~20.04.1) ...
Setting up libpython3.9:amd64 (3.9.5-3~20.04.1) ...
Setting up python3.9-venv (3.9.5-3~20.04.1) ...
Setting up libpython3.9-dev:amd64 (3.9.5-3~20.04.1) ...
Setting up python3.9-dev (3.9.5-3~20.04.1) ...
Processing triggers for man-db (2.9.1-1) ...
Processing triggers for libc-bin (2.31-0ubuntu9.2) ...

```

- 之后步骤和3.8相同
  -  python3.9 -m venv sandbox3.9
  下方例子为：创建sandbox3.9 目录，并激活3.9虚拟环境：

```
python3.9 -m venv sandbox3.9
dnac@ubuntu20:~$ source sandbox3.9/bin/activate
(sandbox3.9) dnac@ubuntu20:~$ python
Python 3.9.5 (default, May 19 2021, 11:32:47) 
[GCC 9.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 
(sandbox3.9) dnac@ubuntu20:~$ pip list
Package       Version
------------- -------
pip           20.0.2 
pkg-resources 0.0.0  
setuptools    44.0.0 
```






