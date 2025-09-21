# 代码使用说明(本项目来自b站[黑马程序员](https://space.bilibili.com/37974444)[redis教程](https://www.bilibili.com/video/BV1cr4y1671t)，仅供参考)

项目代码包含2个分支：
- master : 主分支，包含完整版代码，作为大家的编码参考使用
- init : 初始化分支，实战篇的初始代码，建议大家以这个分支作为自己开发的基础代码
- 前端资源在src/main/resources/nginx-1.18.0下
- develop: 开发分支，从 init 分支拉出的分支，用于开发代码

视频地址:
- [黑马程序员Redis入门到实战教程，深度透析redis底层原理+redis分布式锁+企业解决方案+redis实战](https://www.bilibili.com/video/BV1cr4y1671t)
- [https://www.bilibili.com/video/BV1cr4y1671t](https://www.bilibili.com/video/BV1cr4y1671t)
  - P24起 实战篇

## 1.下载
克隆完整项目：
先fork项目到自己的github仓库，然后clone到本地
```git
git clone https://github.com/gcheng81/hmdp.git
```
切换分支
```git
git checkout init
git checkout -b develop
```
在 develop 分支下进行开发编码

## 2.常见问题
部分同学直接使用了master分支项目来启动，控制台会一直报错:
```
NOGROUP No such key 'stream.orders' or consumer group 'g1' in XREADGROUP with GROUP option
```
这是因为我们完整版代码会尝试访问Redis，连接Redis的Stream。建议同学切换到init分支来开发，如果一定要运行master分支，请先在Redis运行一下命令：
```text
XGROUP CREATE stream.orders g1 $ MKSTREAM
```
