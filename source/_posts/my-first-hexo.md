---
title: my first hexo
date: 2019-04-09 15:20:31
tags: init
---

## 记一次在github上创建hexo博客
首先全局安装hexo的脚手架
```node
npm i -g hexo-cli
```
或npx直接安装项目
```node
npx hexo-cli <youblogname>
```
### github上创建对应的仓库
略
~~据说好的仓库名影响最后的地址，但最后地址还是加上了github的前缀，地址是没法美观了~~
### 本地搭建
1. 使用脚手架创建

2. 创建一个新的博客文档

```node
hexo new 'my first blog'
```
在/source/_posts/ 下生成了markdown文件

3. 将markdown文件转换成html文件

```node
hexo g
```
根据日期在public下生成了对应的html文件


4. 设置远程的仓库地址

打开根目录 _config.yml 修改 deploy后的设置
```
deploy:
  type: git // 大概是类型
  repository: // 远端仓库的地址
  branch: master // 仓库的分支
```

5. 将本地部署至远端

```node
hexo d
```

如此就完成了一次发布

### 修改博客的样式

#### 手动修改

能力有限

#### 下载第三方的主题

[next主题](https://github.com/iissnan/hexo-theme-next "主题地址")
主题样式放在 /themes/ 下
根据介绍选择git安装

```git
$ git clone https://github.com/iissnan/hexo-theme-next themes/next
```

然后在 _config.yml 中修改配置
```
theme: next
```

重新执行上面构建发布的命令就能在线上观察到样式的变化

### 源文件存储
到线上后看到的只有html文件
源文件依旧在本地，若想在其他机器修改博客
还需要把源文件上传远端
可以重新创建一个仓库，再配置上持续集成，形成一条龙服务
不推荐在博客仓库新建分支保存源文件

## 其他

修改配置后可能存在缓存导致线上无变化
需要运行
```node
hexo clean
```
清除缓存

