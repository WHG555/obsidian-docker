# obsidian-docker
在docker中安装了obsidian，可以部署在服务器上，通过网页进行访问

# 使用
>docker run -v /data:/data -p 526:22 -p 6816:6080 -p6818:6090 -p 5926:5900 --rm --device /dev/fuse --privileged obsidian-docker

# 编译
>docker build -t obsidian-docker .


