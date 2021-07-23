
### DNAC template testing

DNAC中使用步骤和方法：

- 步骤一：在DNAC 中增加 Template（菜单：tools->template editor）；
- 步骤二：Design-> network profile 增加site <-> template name之间的关联，注意选day N template；
- 步骤三：菜单 Provision -> device 选择上 -> action -> provision -> provision device，进行设备provision操作，需要注意的是，design network setting相关的配置命令将一起生成，另外配置中还包括高级部分（template 渲染生成的部分），初次使用，请使用*config preview*；
- 步骤四：进入 activity -> work items，查看DNAC生成的配置，如果没问题再deploy，设备配置将下发；

希望推送的命令为：
- license smart deregister
- license smart register idtoken <token>

  
### template中设置exec中运行的命令
由于希望推送的命令为enable 下方执行的命令，不是*configure terminal* 下的配置命令，需要额外提示 DNAC（Template 里面的命令默认是配置命令）。

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
  
  
  
