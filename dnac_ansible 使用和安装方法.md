## 安装方法

[ 先安装、设置Python虚拟环境 ](https://github.com/yijxiang/python-on-ubuntu/blob/main/Python%20虚拟环境%20-%20venv.md )

Ansible 只需要安装 ubuntu 20.04 自带的python3.8系统即可，当然Python 3.9应该也是OK的。

进入到Python虚拟环境之后，就按照下面的 Ansible Galaxy 官方说明，安装下述 packages：
-  pip install ansible
-  pip install dnacentersdk
-  pip install jmespath
-  ansible-galaxy collection install cisco.dnac

安装完成可以通过 pip list，ansible --version 等命令检查是否正常。

- pip list

```
pip list
Package            Version  
------------------ ---------
ansible            4.5.0    
ansible-core       2.11.4   
certifi            2021.5.30
cffi               1.14.6   
charset-normalizer 2.0.4    
cryptography       3.4.8    
dnacentersdk       2.3.1    
fastjsonschema     2.15.1   
future             0.18.2   
idna               3.2      
Jinja2             3.0.1    
MarkupSafe         2.0.1    
packaging          21.0     
pip                20.0.2   
pkg-resources      0.0.0    
pycparser          2.20     
pyparsing          2.4.7    
PyYAML             5.4.1    
requests           2.26.0   
requests-toolbelt  0.9.1    
resolvelib         0.5.4    
setuptools         44.0.0   
urllib3            1.26.6 
```


- ansible-galaxy  collection list

```ansible-galaxy  collection list

# /home/cisco/venv/lib/python3.8/site-packages/ansible_collections
Collection                    Version
----------------------------- -------
amazon.aws                    1.5.0  
ansible.netcommon             2.4.0  
ansible.posix                 1.3.0  
ansible.utils                 2.4.0  
ansible.windows               1.7.2  
arista.eos                    2.2.0  
awx.awx                       19.2.2 
azure.azcollection            1.9.0  
check_point.mgmt              2.0.0  
chocolatey.chocolatey         1.1.0  
cisco.aci                     2.0.0  
cisco.asa                     2.0.3  
cisco.intersight              1.0.17 
cisco.ios                     2.4.0  
cisco.iosxr                   2.4.0  
cisco.meraki                  2.4.2  
cisco.mso                     1.2.0  
cisco.nso                     1.0.3  
cisco.nxos                    2.5.1  
cisco.ucs                     1.6.0  
cloudscale_ch.cloud           2.2.0  
community.aws                 1.5.0  
community.azure               1.0.0  
community.crypto              1.9.2  
community.digitalocean        1.9.0  
community.docker              1.9.1  
community.fortios             1.0.0  
community.general             3.6.0  
community.google              1.0.0  
community.grafana             1.2.1  
community.hashi_vault         1.3.2  
community.hrobot              1.1.1  
community.kubernetes          1.2.1  
community.kubevirt            1.0.0  
community.libvirt             1.0.2  
community.mongodb             1.3.1  
community.mysql               2.1.1  
community.network             3.0.0  
community.okd                 1.1.2  
community.postgresql          1.4.0  
community.proxysql            1.2.0  
community.rabbitmq            1.1.0  
community.routeros            1.2.0  
community.skydive             1.0.0  
community.sops                1.1.0  
community.vmware              1.13.0 
community.windows             1.6.0  
community.zabbix              1.4.0  
containers.podman             1.7.0  
cyberark.conjur               1.1.0  
cyberark.pas                  1.0.7  
dellemc.enterprise_sonic      1.1.0  
dellemc.openmanage            3.6.0  
dellemc.os10                  1.1.1  
dellemc.os6                   1.0.7  
dellemc.os9                   1.0.4  
f5networks.f5_modules         1.11.0 
fortinet.fortimanager         2.1.3  
fortinet.fortios              2.1.2  
frr.frr                       1.0.3  
gluster.gluster               1.0.1  
google.cloud                  1.0.2  
hetzner.hcloud                1.6.0  
hpe.nimble                    1.1.3  
ibm.qradar                    1.0.3  
infinidat.infinibox           1.2.4  
inspur.sm                     1.3.0  
junipernetworks.junos         2.5.0  
kubernetes.core               1.2.1  
mellanox.onyx                 1.0.0  
netapp.aws                    21.6.0 
netapp.azure                  21.8.1 
netapp.cloudmanager           21.9.0 
netapp.elementsw              21.6.1 
netapp.ontap                  21.10.0
netapp.um_info                21.7.0 
netapp_eseries.santricity     1.2.13 
netbox.netbox                 3.1.1  
ngine_io.cloudstack           2.1.0  
ngine_io.exoscale             1.0.0  
ngine_io.vultr                1.1.0  
openstack.cloud               1.5.0  
openvswitch.openvswitch       2.0.0  
ovirt.ovirt                   1.6.2  
purestorage.flasharray        1.10.0 
purestorage.flashblade        1.6.0  
sensu.sensu_go                1.12.0 
servicenow.servicenow         1.0.6  
splunk.es                     1.0.2  
t_systems_mms.icinga_director 1.21.1 
theforeman.foreman            2.2.0  
vyos.vyos                     2.5.1  
wti.remote                    1.0.1  

# /home/cisco/.ansible/collections/ansible_collections
Collection    Version
------------- -------
ansible.utils 2.4.0  
cisco.dnac    3.1.1
```

- 


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

 
 

