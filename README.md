# Lenovo-ThinkCentre-M720Q-i3-9100-Hackintosh

  被EFI包配置为Lenovo ThinkCentre M720Q配i3-9100，无其他额外驱动。可正常使用  
  关于解锁CFG Lock请到Tools目录下[查看教程](https://github.com/psvajaz/Lenovo-ThinkCentre-M720Q-i3-9100-Hackintosh/blob/main/Tools/README.md)  
 

  以下步骤可开启/关闭OpenCore菜单：  
    修改/EFI/OC/config.plist文件中的设置项  
      ShowPicker  :  true/false     开启/关闭OpenCore  
      TimeOut  :  0/1/2/3/4/5...    设定菜单停留时间：0/1/2/3/4/5秒  
 
  以下操作为系统SIP相关  
    修改/EFI/OC/config.plist文件中的设置项  
      csr-active-config  :  0xE7030000  
    进入恢复模式：  
      开启SIP:    csrutil enabled  
      关闭SIP:    csrutil disable  
      查看SIP状态: csrutil status  
 
  开启HiDPI  
    ```
    bash -c "$(curl -fsSL https://raw.githubusercontent.com/xzhih/one-key-hidpi/master/hidpi.sh)"  
    ```
    具体教程请[查看教程](https://github.com/xzhih/one-key-hidpi/blob/master/README-zh.md "查看教程")
