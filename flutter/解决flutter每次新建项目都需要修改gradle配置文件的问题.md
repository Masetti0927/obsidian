# 关键配置文件

## 1.build.gradle
## 2.settings.gradle
## 3. gradle/wrapper/gradle.properties

# 解决办法

- 修改flutter的默认模板
模板位置为
`'X:\x\packages\flutter_tools\templates'

其中，X为盘符，x为flutter_sdk安装目录
修改此文件夹里app子文件夹当中所有的关键配置文件，
1. gradle.properties加入distributionUrl=https\://mirrors.cloud.tencent.com/gradle/gradle-8.10.2-all.zip
2. 其他配置文件加入
3. repositories {  
    // 阿里云镜像  
    maven { url=uri("https://maven.aliyun.com/repository/public/")}  
    // 中科大镜像  
    maven { url=uri("https://mirrors.ustc.edu.cn/maven/releases/")}  
    // 清华大学镜像  
    maven { url=uri("https://mirrors.tuna.tsinghua.edu.cn/nexus/content/repositories/central/")}  
    // 添加其他需要的仓库  
    google()  
    mavenCentral()  
    gradlePluginPortal()  
}

