# obsidian-docker
在docker中安装了obsidian，可以部署在服务器上，通过网页进行访问

# 下载
>docker pull 1002285542/obsidian-docker:v1.0

# 使用
前台使用
>docker run -v /data/vaults:/vaults -v /data/config:/config -p 526:22 -p 6816:6080 -p 6818:6090 -p 5926:5900 -p 27123:27123 -p 27124:27124 --rm --device /dev/fuse --privileged obsidian-docker:v1.0

后台使用
>docker run -d -v /data/vaults:/vaults -v /data/config:/config -p 526:22 -p 6816:6080 -p 6818:6090 -p 5926:5900 -p 27123:27123 -p 27124:27124 --device /dev/fuse --privileged obsidian-docker

# 编译
>docker build -t obsidian-docker .


