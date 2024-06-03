# Minecraft服务端搭建教程
# 本地运行  
## 安装Java运行环境  
### 使用第三方JVM(推荐)  
***本教程基于Ubuntu 22.04运行，如果您使用的是其他的操作系统，请自行研究***
- 下载并安装Azul Zulu  
*以下内容来自Azul官方文档，原地址为<https://docs.azul.com/core/install/debian#install-deb-package>*
  - 导入Azul的apt镜像源  

`
apt -y install gnupg ca-certificates curl
`  

`
curl -s https://repos.azul.com/azul-repo.key | sudo gpg --dearmor -o /usr/share/keyrings/azul.gpg
`  

`
echo "deb [signed-by=/usr/share/keyrings/azul.gpg] https://repos.azul.com/zulu/deb stable main" | sudo tee /etc/apt/sources.list.d/zulu.list
`  

  - 更新apt镜像源  

`
apt -y update
`  

  - 安装zulu  

`
apt -y install zulu21-jdk
`  

  - 查看Java安装信息  

`
java -version
`  


### 使用Oracle官方JVM(不推荐)  
直接使用apt安装即可  

`
apt -y install openjdk-21-jdk
`  
  - 查看Java安装信息  

`
java -version
`  

## 下载Minecraft服务端文件  
***本教程在此处以paper为例，如需使用其他的服务端文件，请自行参考其官方文档进行部署***  
- 前往paper官网下载最新的发行包  
> <https://papermc.io/downloads/paper>  


`
mkdir ./minecraft && cd minecraft
`  

`
wget https://api.papermc.io/v2/projects/paper/versions/1.20.6/builds/115/downloads/paper-1.20.6-115.jar
`  
- 配置JVM并运行  

`
java -jar paper-1.20.6-115.jar
`  

第一次启动会报错，但是会在当前目录下生成EULA.txt文件，我们需要编辑里面的内容  

`
vi EULA.txt
`  

> 将EULA=false改成EULA=true  

再次启动服务端  

`
java -jar paper-1.20.6-115.jar
`  

如果一切没有问题，您应该可以通过Minecraft加入您的服务器了，默认服务器端口为25565，IP为您的服务器IP  

## 进阶部署
由于Minecraft服务端运行在前端，因此您一旦关闭终端窗口，那么您的服务器也会随之关闭  
想要长期运行，您需要使用一些工具将其部署在后端  
本教程以tmux为例，若您使用过其他类似的工具，也可以参考本教程进行分离部署  
安装tmux  

`
apt -y install tmux
`  
> *附：tmux基本用法<https://www.ruanyifeng.com/blog/2019/10/tmux.html>*  

`
tmux new -s minecraft
`  
在新建的分离终端参考上述再次运行mincraft服务端  
大功告成，您现在可以关闭终端窗口了，您的Minecraft服务器依然在运行中  
