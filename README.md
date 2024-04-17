# jsnes 在线游戏机源码

#### 介绍

网页版 fc 模拟器，h5 网页版 NES 模拟器，随时随地体验儿时的乐趣。

<!-- fc.liflag.cn 站点的源码 -->

#### 软件架构

模拟器使用了 jsnes，摇杆使用 nipplejs 进行封装

##### 体验地址

<!-- http://fc.liflag.cn -->

#### 安装教程

1. 将项目目录放在服务器根目录，访问此服务器即可

#### 常规使用说明

1. 将 src 目录下所有文件、lib 目录和 roms 目录复制到服务器根目录即可

   - 即 `cp src/* lib/ roms/ $服务器根目录`

2. 请保留作者标注，谢谢

#### 容器化使用说明

1. 在安装有 jdk 和 docker 的服务器上执行
2. 启动
   - ```shell
     ./gradlew :runDockerContainer
     ```
   - 访问 http://localhost:8081 即可
3. 停止
   - ```shell
     ./gradlew :stopDockerContainer
     ```
4. 若服务器没有公网或无法下载，可以手动打包镜像
   - ```shell
     ./gradlew :buildDockerImage
     ```
5. 镜像推送
   - ```shell
     ./gradlew :pushDockerImage
     ```
6. 若 java sdk 没有安装，无法执行 gradlew 命令；但安装了 docker 也可以手动启动容器
   - ```shell
     docker run --rm -p 8081:80 --name jsnes -d wangz2019/jsnes:1.0.0
     ```
   - 使用 `docker kill jsnes` 来停止

#### 文档站点化

1. 可以使用 pages 直接开启文档站点（选择根目录即可）
2. 也可以使用命令在服务器上启动或停止
   - ```shell
     ./gradlew :startDocsNginxDocker
     ```
   - ```shell
     ./gradlew :stopDocsNginxDocker
     ```

#### 更新日志

2024.04.10 容器化、文档站点化

2024.04.05 集成 nipplejs.js

    方向键改为摇杆操作， 感谢 root@isgjl.cn 贡献的代码
