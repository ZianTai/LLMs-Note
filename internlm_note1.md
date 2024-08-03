# 入门岛
## 第一关 Linux基础知识
### 1. 创建开发机
**Docker容器：** 包含运行一个应用程序的依赖，并实现了计算资源的隔离
**Docker镜像：** 是容器的构建模板，可以理解为容器的运行环境，是一个轻量级的、可执行的软件包，包含了软件所需要的依赖项和配置文件

### 2. SSH远程连接开发机

1. 使用 ` ssh-keygen -t rsa -b 4096 -C "your_email@example.com ` 生成SSH密钥对，其中：
-t：指定密钥类型，如dsa、ecdsa、ed25519、rsa
-b：指定密钥长度
-C：添加注释
2. 将公钥添加到服务器 `ssh-copy-id username@remote_host`

`
### 3. 使用VScode进行远程连接
1. 安装**Remote-SSH**插件
2. 在SSH中点击“+”按钮，添加开发机SSH连接的登录命令。

### 4. 完成端口映射，运行“hello_world.py”
端口映射：将外网中的任意端口映射到内网中的相应端口，实现内外端口之间的通信，通过端口通信，可以在外网访问内网中的服务或者应用。
配置端口映射的hello_world运行结果：
![未进行端口映射](https://i-blog.csdnimg.cn/direct/91e4a81ac3594ceda44efc101f63c309.png)


### 5. 使用VScode远程连接开发机并创建一个conda环境

新建一个虚拟环境，使用命令
`conda create -n envname python=3.10`
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/ebc389bad89a44c4a34cd3d0e8ed5a9e.png)
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/8aaffba8664d4b72a722565929f0d98b.png)


导出虚拟环境（因为有些软件包的依赖关系很复杂，如果自己重新进行创建和配置的话很麻烦，如果我们将配置好的环境导出，这样下次使用还原就行了，而且也可以把配置分享给其他人。）

使用命令：
`conda env export --name myenv > myenv.yml`

重新还原环境，使用命令：
`conda env create -f  myenv.yml`





