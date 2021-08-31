## 安装方法

先安装、设置Python虚拟环境。

之后，按照Ansible Galaxy 说明，安装下述packages：
- sudo pip install ansible
- sudo pip install dnacentersdk
- ansible-galaxy collection install cisco.dnac


## 使用方法

#### 步骤一，创建文件

先创建3个文件：

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

#### 步骤二，运行playbook

执行ansible playbook：

```
ansible-playbook -i hosts main.yml
```



### 参考链接 links

- [ Ansible Galaxy: https://galaxy.ansible.com/cisco/dnac ](https://galaxy.ansible.com/cisco/dnac)
- [ Ansible Modules for DNA Center 使用手册 ](https://developer.cisco.com/docs/dna-center/?utm_campaign=dnac-padm&utm_source=padm-ww&utm_medium=dnac-blog-docs#!ansible )
- [ DNAC Ansible Github 源代码 ]( https://github.com/cisco-en-programmability/dnacenter-ansible)
- [   ]( )
- [   ]( )
- [   ]( )
- [   ]( )
 
 

