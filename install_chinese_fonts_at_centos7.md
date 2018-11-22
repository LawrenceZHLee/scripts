1、安装必备软件包
```Bash
sudo yum -y install fontconfig ttmkfdir
```
2、将中文字体包上传至目标服务器并拷贝到字体目录，并修改权限：
```Bash
sudo cp -r /path/to/chinese-fts /usr/share/fonts
sudo chmod -R 755 /usr/share/fonts/chinese-fts
```
3、使用ttmkfdir汇总生成fonts.scale文件
```Bash
sudo ttmkfdir -e /usr/share/X11/fonts/encodings/encodings.dir
```
4、修改字体配置文件
```Bash
sudo vim /etc/fonts/fonts.conf
```
类似这样
```Bash
        <dir>/usr/share/fonts</dir>
        <dir>/usr/share/fonts/chinese-fts</dir>
```  
然后输入:wq!保存退出

5、最后重建字体缓存（不用重启服务器）
```Bash
sudo fc-cache
```
