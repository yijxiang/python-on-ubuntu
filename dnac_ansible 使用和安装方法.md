## 安装方法

[ 先安装、设置Python虚拟环境 ](https://github.com/yijxiang/python-on-ubuntu/blob/main/Python%20虚拟环境%20-%20venv.md )

Ansible 只需要安装 ubuntu 20.04 自带的python3.8系统即可，当然Python 3.9应该也是OK的。

进入到Python虚拟环境之后，就按照下面的 Ansible Galaxy 官方说明，安装下述 packages：
- sudo pip install ansible
- sudo pip install dnacentersdk
- ansible-galaxy collection install cisco.dnac

安装完成可以通过 pip list，ansible --version 等命令检查是否正常。


## 使用方法

#### 步骤一，创建文件

在项目目录下，先创建3个文件：

- hosts

该文件内容为，其格式为ini：

```
[dnac_servers]
dnac_server
```


- credentials.yml

该文件内容为YAML格式的文件，请按实际情况修改其具体参数：

```
---
dnac_host: <A.B.C.D>
dnac_port: 443   # optional, defaults to 443
dnac_username: <username>
dnac_password: <password>
dnac_version: 2.2.2.3   # optional, defaults to 2.2.2.3
dnac_verify: False     # optional, defaults to True
dnac_debug: False     # optional, defaults to False
```


- main.yml

该文件内容为YAML格式的文件，主要是ansible task，实现从DNAC中获取设备资产信息表：

```
---
- hosts: dnac_servers
  vars_files:
    - credentials.yml
  gather_facts: no
  tasks:
  - name: Get Network Devices
    cisco.dnac.network_device_info:
      dnac_host: "{{dnac_host}}"
      dnac_username: "{{dnac_username}}"
      dnac_password: "{{dnac_password}}"
      dnac_verify: "{{dnac_verify}}"
      dnac_port: "{{dnac_port}}"
      dnac_version: "{{dnac_version}}"
      dnac_debug: "{{dnac_debug}}"
    register: network_devices_result

  - name: Show all network_devices
    ansible.builtin.debug:
      msg: "{{ network_devices_result }}"
```

#### 步骤二，运行 ansible playbook

执行ansible playbook：

```
ansible-playbook -i hosts main.yml
```

注意观察 ansible 运行是否正常，由于该task仅仅获取信息，所以 Ansible result 正常情况下绿色显示。
Ansible debug 模块是把结果打印输出，以便我们检查信息采集收否正常。



### 参考链接 links

- [ Ansible Galaxy: https://galaxy.ansible.com/cisco/dnac ](https://galaxy.ansible.com/cisco/dnac)
- [ Ansible Modules for DNA Center 使用手册 ](https://developer.cisco.com/docs/dna-center/?utm_campaign=dnac-padm&utm_source=padm-ww&utm_medium=dnac-blog-docs#!ansible )
- [ DNAC Ansible Github 源代码 ]( https://github.com/cisco-en-programmability/dnacenter-ansible)
- [   ]( )
- [   ]( )
- [   ]( )

 
 

