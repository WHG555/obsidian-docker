# 说明  
说明::本镜像是一个将obsidian，安装在一个有桌面的docker系统。使用这个镜像，可以将obsidian嵌入到网页当中，进行使用。支持中文展示与中文输入。
# 简单使用
下载运行镜像
> docker run -p 6818:6090 --device /dev/fuse --privileged hcyxsmile/obsidian-docker:v1.0

运行启动完成后，打开下面的链接： 默认密码是：`123456`  
>https://192.168.55.25:6818/vnc.html 

（IP需要使用自己装docker镜像的IP）


![](https://files.mdnice.com/user/18211/ef97c37d-6690-474b-864c-013803b50d20.png)


恭喜你，可以开始obsidian的网上使用之旅了。

# 更多的配置
## 登陆方式修改
这个docker仓库是支持ssh、VNC、网页三种方式登陆的。想要使用其中的登陆方式，我们需要修改一下启动命令。
- 只使用ssh登陆方式
> docker run -p 526:22 --device /dev/fuse --privileged hcyxsmile/obsidian-docker:v1.0
- 只使用VNC登陆方式
> docker run -p 5926:5900 --device /dev/fuse --privileged hcyxsmile/obsidian-docker:v1.0
- 只使用网页登陆方式
> docker run -p 6818:6090 --device /dev/fuse --privileged hcyxsmile/obsidian-docker:v1.0
- 使用ssh、VNC、网页登陆三种方式
> docker run -p 526:22 -p 5926:5900 -p 6818:6090 --device /dev/fuse --privileged hcyxsmile/obsidian-docker:v1.0

## 后台启动方式
docker可以将镜像以后台的方式运行，添加参数 `-d`  
>docker run -d -p 6818:6090 --device /dev/fuse --privileged hcyxsmile/obsidian-docker:v1.0

## 修改密码
ssh、VNC、网页都是有密码的，默认密码为：`123456`  
我们要改密码的话，需要在启动命令中添加 `-e PASSWD=abcd1234`，新密码就变成 `abcd1234`  
> docker run -p 6818:6090  -e PASSWD=abcd1234 --device /dev/fuse --privileged hcyxsmile/obsidian-docker:v1.0

## 修改分辨率
修改分辨率的话，需要在启动命令中添加 `-e SIZE=1024x768`  
> docker run -p 6818:6090  -e SIZE=1024x768 --device /dev/fuse --privileged hcyxsmile/obsidian-docker:v1.0

## 挂载自己的目录到docker中
我们可以将自己主机中的目录，挂载到docker中，这样数据就不会丢失。  
主机的目录为`/data/vaults`  
docker中的目录为 `/vaults`  
> docker run  -v /data/vaults:/vaults -p 6818:6090  --device /dev/fuse --privileged hcyxsmile/obsidian-docker:v1.0


# 环境配置
obsidian-docker：v1.0  
obsidian：1.0.0



