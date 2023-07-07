### [简体中文](README.md) | ENGLISH


Build a smoother remote office environment than remote desktop based on VSCODE and DOCKER


The complexity of the whole process is similar to the first contact with virtual machines. It is recommended to experience [Github CodeSpaces](https://docs.github.com/zh/codespaces/developing-in-codespaces/using-github-codespaces-in-visual-studio-code) first


This article is designed to help you create a CodeSpaces of your own


----------
### Official Tutorial
[Run and debug in a local docker container using VsCode](https://code.visualstudio.com/docs/remote/ssh)，


[Run, debug in remote docker containers with VsCode](https://code.visualstudio.com/remote/advancedcontainers/develop-remote-host)


There is a serious problem with the official remote container version of the tutorial: [DOCKER_HOST not work](https://github.com/microsoft/vscode-dev-containers/issues/1753)


----------
### Easy Tutorial ([If you encounter a problem](https://github.com/LI-GUOJIE/vscode-remote-dev-container/issues))
##### Cloud Server Environment Preparation
```
1. Install Docker
2. Add docker operation permissions to user
3. Install SSH, set up key login for user
4. Create a directory to mount to the container, for example: /home/egg/docker/vscode/
```


##### Local PC environment preparation
```
1. Install Docker Desktop (Actually, only docker-cli is used, no need for docker-ce)
2. Install VSCODE and [dev container] plugin
3. Set up SSH alias login
```


##### Create a remote container (doing this on VSCODE on the local PC)
```
1. git clone https://github.com/LI-GUOJIE/vscode-remote-dev-container
2. Open the directory using VSCODE
3. Modify the [workspaceFolder], [workspaceMount] in .devcontainer/devcontainer.json
4. Modify the [docker.host] in .vscode/settings.json
5. Click on the [dev container] icon in the bottom left corner of VSCODE, select [Reopen in container], and wait for a while.
```


##### Continue working on new device
```
1. Install Docker Desktop (Actually, only docker-cli is used, no need for docker-ce)
2. Install VSCODE and [dev container] plugin
3. Open User Settings(json), and add [docker.host]
4. Verify that the remote container is running via VSCODE's Terminal
5. Click on the [dev container] icon in the bottom left corner of VSCODE, select [Attach to runnning container], and wait for a while.
```


##### Add New Users
```
1. It is recommended to use VMs (virtual machines) to isolate different users
2. Or append Volumn to the container for new users, each with their own storage space, but not completely isolated from each other
```





