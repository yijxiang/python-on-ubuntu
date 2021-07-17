### Python 虚拟环境设置

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




