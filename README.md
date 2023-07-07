### 简体中文 | [ENGLISH](README.en-US.md)


基于 VSCODE 和 DOCKER ，搭建一个比远程桌面更流畅的远程办公环境


整个过程的复杂度，和第一次接触虚拟机差不多。建议先体验 [Github CodeSpaces](https://docs.github.com/zh/codespaces/developing-in-codespaces/using-github-codespaces-in-visual-studio-code) ，确定这是你想要的东西


本文旨在帮助你创建一个属于你自己的 CodeSpaces


----------
### 官方教程
[使用VsCode在本地docker容器中运行、调试](https://code.visualstudio.com/docs/remote/ssh)


[使用VsCode在远程docker容器中运行、调试](https://code.visualstudio.com/remote/advancedcontainers/develop-remote-host)


官方远程容器版教程存在一个严重问题：[DOCKER_HOST不起作用](https://github.com/microsoft/vscode-dev-containers/issues/1753)


----------
### 突然想到了一个更简单的方法
```
1. 云服务器上创建docker容器
2. 在docker容器中安装SSH服务
3. 在本地PC上，仅需安装 VSCODE 以及 REMOTE SSH 插件
```

----------
### 旧的简易教程（[遇到问题](https://github.com/LI-GUOJIE/vscode-remote-dev-container/issues)）
##### 云服务器环境准备
```
1. 安装完整版的docker
2. 为user添加docker操作权限
3. 安装SSH，为user设置秘钥登录，这一步是为了方便后续使用别名访问云服务器
4. 创建一个目录，用于挂载到容器，比如/home/egg/docker/vscode/
```


##### 本地PC环境准备
```
1. 安装 Docker Desktop（其实只用到docker-cli, 无需docker-ce）
2. 安装 VSCODE 以及 dev container 插件
3. 设置SSH别名登录
```


##### 创建远程容器（在本地PC 的 VSCODE 上进行操作）
```
1. git clone https://github.com/LI-GUOJIE/vscode-remote-dev-container
2. 使用 VSCODE 打开该目录
3. 修改 .devcontainer/devcontainer.json 中的 workspaceFolder、workspaceMount
4. 修改 .vscode/settings.json 中的 docker.host
5. 点击 VSCODE 左下角的【dev container】图标，选择【Reopen in container】，等待一段时间即可
```


##### 在新设备上继续工作
```
1. 安装 Docker Desktop（其实只用到docker-cli, 无需docker-ce）
2. 安装 VSCODE 以及 dev container 插件
3. 打开 VSCODE 的 USER级别 的 settings.json，添加 docker.host
4. 通过 VSCODE 的 Terminal 确认远程容器已启动
5. 点击 VSCODE 左下角的【dev container】图标，选择【Attach to runnning container】，等待一段时间即可
```


##### 添加新用户
```
1. 建议使用虚拟机（VM）对不同用户进行隔离
2. 或者在容器中为新用户追加Volumn，每个用户拥有属于自己的存储空间，但彼此之间并非完全隔离
```


## License

Copyright © Microsoft Corporation All rights reserved.<br />
Licensed under the MIT License. See LICENSE in the project root for license information.
