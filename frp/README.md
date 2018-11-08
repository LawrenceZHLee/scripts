服务器端和客户端都以linux_x86-64示例（centos、ubuntu等）

# 服务器端

1、下载frp程序文件并解压
```Bash
wget https://github.com/fatedier/frp/releases/download/v0.21.0/frp_0.21.0_linux_amd64.tar.gz
tar -zxvf frp_0.21.0_linux_amd64.tar.gz frp_0.21.0_linux_amd64
```
2、复制frps启动命令及配置文件到系统相应目录：
```Bash
sudo cp -r frp_0.21.0_linux_amd64 /usr/local/frp
```
3、复制配置文件frps.ini到frp目录
```Bash
sudo cp frps.service /usr/local/frp
```
4、复制自启服务frps.service文件并启用
```Bash
sudo cp frps.service /usr/lib/systemd/system

sudo systemctl enable frps
```
#查看服务是否生效
```Bash
sudo systemctl list-units |grep frps
```

# 客户端

1、下载 https://github.com/fatedier/frp/releases/download/v0.21.0/frp_0.21.0_linux_amd64.tar.gz

2、复制frps启动命令及配置文件到系统相应目录：
```Bash
sudo cp -r frp_0.21.0_linux_amd64 /usr/local/frp
```
3、复制配置文件frpc.ini到frp目录
```Bash
sudo cp frpc.service /usr/local/frp
```
4、复制自启服务frpc.service文件并启用
```Bash
sudo cp frpc.service /usr/lib/systemd/system

sudo systemctl enable frpc
```
#查看服务是否生效
```Bash
sudo systemctl list-units |grep frpc
```
# 服务器端和客户端要开启对应的接口
