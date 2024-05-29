# Minecraft服务端搭建教程
## 本地运行  
### 安装Java运行环境  
#### 使用第三方JVM(推荐)  
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
  - 安装zulu17  
`  
apt -y install zulu17-jdk   
`  
  - 查看Java安装信息
`  
java --version
`  


#### 使用Oracle官方JVM(不推荐)  
直接使用apt安装即可  
`
apt -y install openjdk-17-jdk  
`
