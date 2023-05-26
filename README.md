# rust-vscode-dev-docker
开箱即用的rust开发环境，开发工具vscode web版,配合插件rust-analyzer和CodeLLDB来做语法高亮分析和debug

## 开发环境组成
* Ubuntu 22.04.1 LTS
* GNU Make 4.3
* rustc nightly-latest
* rustup latest
* cargo nightly-latest
* code-server 4.13.0
* code-server extensions
    * rust-analyzer v0.4.1529
    * CodeLLDB v1.9.1

## 快速开始

运行docker客户端，输入
```
docker pull lyrisdocker/rust-dev:1.1
```
镜像成功拉取后，执行
```
docker run -d --privileged -p 8888:8080 lyrisdocker/rust-dev:1.1
```
这时使用浏览器打开 http://localhost:8888 即可启动开发环境。

后续可以在 Docker客户端中控制已创建容器的暂停与开启。

假设代码在/data/rst-proj 目录，则可以把工作目录附上去
```
docker run -d --privileged -v /data/rst-proj:/root/rst-proj -w /root/rst-proj -p 8888:8080 lyrisdocker/rust-dev:1.1
```
然后就可以在浏览器里面打开工作目录进行编码和设置断点调试了
