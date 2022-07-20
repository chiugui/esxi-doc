**注意：esxi7.0 添加rtl8168网卡驱动失败，没有对应版本的驱动更新到esxi7.0，目前（2022.7.20）只支持到esxi6.7**



ESXI下载：

参考教程：https://docs.vmware.com/cn/VMware-vSphere/7.0/com.vmware.esxi.install.doc/GUID-016E39C1-E8DB-486A-A235-55CAB242C351.html



ESXI7.0添加驱动相关教程：

https://soulteary.com/2021/06/22/nuc-notes-install-esxi7.html
https://customerconnect.vmware.com/cn/group/vmware/evalcenter?p=free-esxi7&source=dwnp



具体步骤：

1.官方下载ESXI-离线包（登录vmware账号）
https://customerconnect.vmware.com/cn/web/vmware/evalcenter?p=free-esxi7&source=dwnp

2.官方下载vmware-powercli
https://developer.vmware.com/web/tool/12.7.0/vmware-powercli
https://developer.vmware.com/powercli/installation-guide

3.ESXi-Customizer-PS.ps1 脚本融合软件 github地址下载
https://github.com/VFrontDe/ESXi-Customizer-PS

4.下载驱动

5.生成iso文件
 .\ESXi-Customizer-PS.ps1 -izip .\VMware-ESXi-7.0U3f-20036589-depot.zip -pkgDir "D:\esxi7\vib"


以管理员权限执行命令如下：
 .\ESXi-Customizer-PS.ps1  -v70 -vft  -load net55-r8168

.\ESXi-Customizer-PS-v2.6.0.ps1 -v67 -vft -load net55-r8168
-v67表示ESXi版本为6.7；
-vft表示从网站 https://vibsdepot.v-front.de/ 中下载
-load表示添加net55-r8168驱动

参考：
https://github.com/chenjun1989/About-VMware-ESXi-7
https://protectli.com/kb/how-to-add-i225-support-for-esxi7/
https://soulteary.com/2021/06/22/nuc-notes-install-esxi7.html
https://www.vediotalk.com/archives/12070
https://github.com/jonas-werner/custom-esxi-iso-with-network-drivers/blob/main/createCustomEsxiInstallerImage.ps1



