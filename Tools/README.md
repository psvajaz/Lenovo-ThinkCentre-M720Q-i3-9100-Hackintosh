配置需要使用的工具

Hackintool                          3.4.4

UEFITool                            A57     导出Bios数据

ifrextractor                        1.0.2   Bios解包工具

LENOVO-M1UKT57A.rom                         M720Q Bios

Universal BIOS Backup ToolKit 2.0   1.0     Windows提取BIOS


解锁CFG Lock(适用于Bios中没有CFG Lock选项的主板) ：
  ***本教程是修改主板固件信息，操作失误会导致Bios崩溃，如果出现崩溃，本人不承担任何责任，请谨慎操作***
  1、使用UEFITool打开Bios文件（LENOVO-M1UKT57A.rom:在Windows下使用BIOS BackUp ToolKit工具进行备份本机Bios）
  2、查找Text “CFG Lock”。如果下方的列表框有出现查找结果，说明Bios支持CFG Lock解锁。双击下方的结果会出现"Setup"，右键点击"Setup"，点击菜单菜单栏中的"Extract as is..."，选择导出位置(与ifrextractor工具相同目录)，并将文件名设定为"setup.bin"。
  3、进入终端，并且在终端中进入"setup.bin"保存的目录，并输入一下命令“./ifrextract setup.bin setup.txt"将解包工具导出的bin文件转换为纯文本文件
  4、用文本编辑器打开setup.txt并搜索"CFG Lock"，可以找到CFG Lock对应的地址 "VarStoreInfo (VarOffset/VarName): 0x721"，其中"0x721"为我们需要的地址，先记录下来(相同机型不同Bios地址都可能不一样)。
  5、在引导菜单中使用modGRUBShell.efi这个工具，进入工具后，输入：“setup_var 0x721 0x00" ，其中0x721为上一步获取的地址请自行修改，0x00为关闭｜0x01为打开  
      ***确定参数和地址的正确，此操作有风险，后果自负！！！！！！能正常使用不建议修改***
  6、操作完成后输入"reboot"重启电脑
  7、在引导菜单中使用VerifyMsrE2.efi进行校验，最后一句出现"This firmware has UNLOCKED MSR 0xE2 register!"即解锁成功。
  8、将/EFI/OC/config.plist文件删除或重命名为其他名称，将"/EFI/OC/config(解锁CFG生产环境).plist"文件改名为"/EFI/OC/config.plist"重新进入系统即可
  
注：本解锁教程应用自司波图的视频教程(https://www.bilibili.com/video/BV1mT4y137T1)15:58~17:25
  
  
