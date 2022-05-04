 # 简略步骤
 ### 配置环境
 ### 配置GenshinSever
 - 克隆项目到本地
 - 编译项目打包jar
 - 运行<br>
 以上均在Ubuntu下使用
 ## 克隆项目到本地
 ```bash
 apt install unzip
 ```
 克隆解压一步到位
  ```bash
 cd ~&&wget https://github.com/Grasscutters/Grasscutter/archive/refs/heads/development.zip&&unzip ./development.zip -d ./&&rm ./development.zip
  ```
在主目录应该是能看见一个Grasscutter-development文件夹了
## 编译项目打包出jar
``` bash
cd ~/Grasscutter-development/
chmod +x ./gradlew
bash ./gradlew jar
```
