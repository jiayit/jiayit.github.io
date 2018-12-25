# 搭建自己的博客

一、准备工作

- 创建Github的账户 

- 安装Node.js、Git、

- 在本地配置好Git [参考链接](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)

二、搭建Github博客

1、新建一个名为 username.github.io的仓库 其中username是你的用户名

2、使用hexo（hexo和Jekyll 都是静态博客框架，有很多好看的模板和主题）

**步骤一**  安装hexo

	$ npm install -g hexo

   小tips：安装node.js要配置好环境变量，使其命令可以全局使用

**步骤二**  初始化

新建一个文件夹 在该文件夹下右键git bash 打开命令行

	$ hexo init
   
该文件夹下会生成一些目录，然后

    $ hexo gernate //可缩写成 hexo g
	$ hexo server  //可缩写成 hexo s

hexo server命令是启动本地服务，打开[http://localhost:4000](http://localhost:4000)可看到生成的博客内容

3、修改主题

我用的是 [hexo-theme-yilia](https://github.com/litten/hexo-theme-yilia)主题

**步骤一**	下载源码

	$ cd /d/hexo/themes/
	$ git clone https://github.com/litten/hexo-theme-yilia.git themes/yilia
	
**步骤二**  修改_config.yml

将里面的
	
	theme: landscape 改为 theme: yillia
**步骤三** 上传github

首先配置好了ssh key
接下来修改_config.yml 中deploy的部分

	deploy:
		type: git
		repository: git@github.com:`username`/`username`.github.io.git
		branch: master

然后安装插件

	$ npm install hexo-deployer-git --save

最后提交到远程库
	
	$ hexo d