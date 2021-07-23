
### DNAC template demo testing

- 在DNAC 中增加template（tools->template editor）
- 

- license smart deregister
- license smart register idtoken <token>

  
### template中设置exec中运行的命令
在enable 下方执行的命令，不是conf t 下的配置命令。

``` 
#MODE_ENABLE
<<commands>>
#MODE_END_ENABLE

#INTERACTIVE
CLI Command<IQ>interactive question 1 <R> command response 1 <IQ>interactive question 2<R>command response 2
no crypto pki trustpoint DNAC-CA<IQ>yes/no<R>yes
#ENDS_INTERACTIVE
```
  
### 例子
  
```
#MODE_ENABLE
license smart deregister
#MODE_END_ENABLE  
```  
  
  
### 检查方法
```  
  show history all | i license
```

 ### URL 资源
  
- [Create Templates to Automate Device Configuration Changes](https://www.cisco.com/c/en/us/td/docs/cloud-systems-management/network-automation-and-management/dna-center/2-1-2/user_guide/b_cisco_dna_center_ug_2_1_2/b_cisco_dna_center_ug_2_1_1_chapter_01000.html)
  
-  [Jinja2](https://www.palletsprojects.com/p/jinja/)
  
- [DNAC-TemplateProgrammer](https://github.com/CiscoDevNet/DNAC-TemplateProgrammer)
  
  
  
