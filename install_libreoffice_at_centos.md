本脚本是为了linux下docx转pdf所需的libreoffice的安装及配置

1、安装libreoffice-core（安装core即可，不用安装全版本）
```Bash
sudo yum -y install libreoffice-core
```
2、配置后台服务及端口监听
```Bash
sudo vim /etc/init.d/soffice
```
```Bash
内容如下：
#!/bin/bash
/usr/lib64/libreoffice/program/soffice -headless -accept="socket,host=127.0.0.1,port=8100;urp;" -nofirststartwizard &
```
4、修改权限及加入自启列表
```Bash
sudo chmod 755 soffice
sudo chkconfig --add soffice
sudo chkconfig soffice on
```
5、查看服务及端口运行情况
```Bash
sudo ps aux|grep soffice
```
