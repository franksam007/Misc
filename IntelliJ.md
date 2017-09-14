IDEA版本：

IntelliJ IDEA 2017.2
Build #IU-172.3317.76, built on July 15, 2017
Licensed to Administrator

JRE: 1.8.0_152-release-915-b5 amd64
JVM: OpenJDK 64-Bit Server VM by JetBrains s.r.o
Windows 7 6.1

### 1. 激活
IntelliJ IDEA下载地址：https://www.jetbrains.com/idea/download/#section=windows
IntelliJ IDEA 是Java开发利器，用社区版不爽，干催就用旗舰版，这个是收费的，需要licence。 

在线激活地址： http://idea.lanyus.com/  或者 https://www.iteblog.com/idea/
本地证书服务器版，压缩包地址：https://pan.baidu.com/s/1eR7KDrk 密码: yguf 
(或者 ？ https://coding.net/u/privatelo/p/lightjbl-release/git   https://coding.net/u/privatelo/p/lightjbl/git)

   1. 解压后，根据系统的类型、运行位数，选择对应的版本，先不启动IDEA，执行相应OS的License服务器。
   2. 启动服务，获取激活地址：http://127.0.0.1:1017
   3. 启动IDEA，打开注册菜单，选择本地licence服务器，输入本地服务器地址
   4. 激活成功
   
### 2. 注册exe为服务
如上，每次开机后都需要启动IntelliJIDEALicenseServer，为了方便起见，我们可以把window的exe程序注册成随机启动的服务。
使用srvany.exe将程序安装成windows服务的详细教程(http://www.cnblogs.com/phpdragon/p/3713517.html)，把exe注册为服务。这样每次启动idea的时候就不用再点击exe了。 

Linux或UNIX，可利用RC脚本
