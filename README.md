 # 简略步骤（因本人学业问题，这个教材腰斩了。没做完）也没有补上的想法
 ### 配置环境
  - 安装[ZeroTermux](https://github.com/hanxinhao000/ZeroTermux)
  - 安装[Ubuntu](https://github.com/MFDGaming/ubuntu-in-termux)
  - 安装MongoDB v5.0
  - 安装JDK17
  - 安装mitmdump
  - 更改wifi代理
 ### [配置GenshinSever](https://github.com/jixiaolou/GenshinSever-in-Termux/blob/main/Deploy.GenshinSever.md)
 
 ## 安装Ubuntu
 1. **安装依赖**
    ```bash ....  
    pkg update && apt-get upgrade -y
    pkg install wget -y
    pkg install proot -y
    pkg install git -y
    ```
2. **执行安装脚本**
    ```bash
    cd ~
    git clone https://github.com/MFDGaming/ubuntu-in-termux.git
    cd ubuntu-in-termux
    chmod +x ubuntu.sh
    ./ubuntu.sh -y
    ```
3. **安装成功执行**
    ```bash
    ./startubuntu.sh
    ```

## 安装MongoDB
1. 初启动Ubuntu需要刷新apt
    ```bash
    apt update
    apt upgrade
    ```
2. 安装MongoDB所需要的依赖
    ```bash
    apt install dirmngr gnupg apt-transport-https ca-certificates software-properties-common wget
    ```
3. 安装证书
    ```bash
    wget -qO- https://www.mongodb.org/static/pgp/server-5.0.asc | gpg --dearmor > /etc/apt/trusted.gpg.d/mongo.gpg
    ```
4. 然后添加安装MongoDB的源
    ```bash
    echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/5.0 multiverse" | tee /etc/apt/sources.list.d/mongodb-org-5.0.list
    ```
5. 然后刷新一下
    ```bash
    apt update
    ```
6. 安装MongoDB
    ```bash
    apt install -y mongodb-org
    ```
7. **第一个问题：没有默认数据库存放文件夹**
    ```bash
    mkdir -p /data/db
    chmod 777 /data/db
    ```
8. **第二个问题：没有libssl1.1**
    - 下载我上传的[libssl1.1](https://github.com/jixiaolou/GenshinSever-in-Termux/releases/download/file/libssl1.1_1.1.1l-1ubuntu1_arm64.deb)
    - 使用**apt install 文件完整路径**安装
        ```bash
        apt install /storage/emulated/0/Download/libssl1.1_1.1.1l-1ubuntu1_arm64.deb
        ```
----

    启动命令mongod
    关闭ctrl+c
## 安装JDK17
```bash
apt install -y openjdk-17-jdk
```
检验是否安装成功
```shell
java -version
```
![正确](https://raw.githubusercontent.com/jixiaolou/GenshinSever-in-Termux/main/IMG_20220504_150203.jpg)
## 安装mitmdump
```shell
apt install -y mitmdump
```
----
做到这里已经配置完了，基本的东西已经装好了。
可以转到配置GenshinSever这一阶段了。在上面简略步骤下
