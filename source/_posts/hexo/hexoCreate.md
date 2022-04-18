---
title: hexo的基础搭建
date: 2021-11-18 23:03:11
categories:
- hexo
tags:
- hexo
- github

index_img:
- ../../img/hexo.jpg
---
## Hexo介绍
Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 Markdown（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。


- 风一般的速度 
Hexo基于Node.js，支持多进程，几百篇文章也可以秒生成。 
- 流畅的撰写 
支持GitHub Flavored Markdown和所有Octopress的插件。 
- 扩展性 
Hexo支持EJS、Swig和Stylus。通过插件支持Haml、Jade和Less.

## 搭建准备
- 所需环境
  - [Node.js](http://nodejs.cn/api/ "Nodejsの中文镜像网站")
  - [git](https://git-scm.com/ "git官网")
- 所需工具
  - [github](https://github.com/ "最大的同性交友网站")
  - [hexo](https://hexo.io/zh-cn/ "hexo中文官网")

## 开始搭建
<div class="flex-start nano-flex-start-align-end "> 
  <img src="../../img/rocket.png" />
  <font size=5 face='微软雅黑' color="#1f87dd" style="font-weight:700;"> fist-step </font>
</div>
<ul class="nano-ul-flex">
  <li>
    <div >安装hexo脚手架</div>
    <div class="nano-pointer">npm install -g hexo-cli</div>
    <hr />
  </li>
   <li>
    <div >初始化hexo文件夹</div>
    <div class="nano-pointer">hexo init (初始化hexo)</div>
    <div class="nano-pointer">npm install</div>
    <hr />
    <img src="../../img/hexo-step1.png"/>
    <div class="nano-tips"><span>Tips:</span> 如果出现报错,一般都是node版本过低导致,升级一下node版本就可以了(博主的node版本是v14.18.1)</div>
    <hr />
  </li>
  <li>
    <div >本地启动hexo</div>
    <div class="nano-pointer">hexo g (生成hexo)</div>
    <div class="nano-pointer">hexo s (启动本地服务器,这一步之后就可以通过http://localhost:4000 查看)</div>
    <img src="../../img/hexo-step2.png"/>
    <div>&nbsp;</div>
    <img src="../../img/hexo-step3.png"/>
    <div class="nano-success">
    <img src="../../img/success-new.png" />
    这样就暂时先完成了本地博客的环境搭建啦~</div>
    <div class="nano-tips"><span>Tips:</span> 如果出现端口占用问题可以输入
      <font size=4 face='微软雅黑' color="#1f87dd" style="font-weight:700;" class="nano-pointer">hexo s -p 41</font>
      暂时切换端口
    </div>
    <hr />
  </li>
</ul> 
<div class="flex-start nano-flex-start-align-end "> 
  <img src="../../img/rocket.png">
  <font size=5 face='微软雅黑' color="#1f87dd" style="font-weight:700;"> twice-step </font>
</div>
<ul class="nano-ul-flex">
  <li>
    <a href="https://github.com/">创建github账号</a>
  </li>
  <li>
   <span>创建一个新的github仓库</span>
   <img src="../../img/github-create-1.png" />
   <hr />
   <img src="../../img/github-create-2.png" />
    <hr />
    <img src="../../img/github-create-3.png" />
    <div class="nano-success">
      <img src="../../img/success-new.png" />
    这样就完成了github的环境配置了~</div>
  </li>
</ul>
<div class="flex-start nano-flex-start-align-end "> 
  <img src="../../img/rocket.png" />
  <font size=5 face='微软雅黑' color="#1f87dd" style="font-weight:700;"> third-step </font>
</div>
<ul class="nano-ul-flex">
  <li>
    <div >配置本地hexo部署到GitHub的文件</div>
    <div>
      编辑根目录下_config.yml文件,查找并切换到deploy字段位置,如图进行编辑:
    </div>
    <img src="../../img/push-hexo1.png" />
    <div class="nano-pd">
      保存后安装扩展: <span class="nano-pointer">npm install hexo-deployer-git --save </span>  
    </div>
    <div class="nano-tips"><span>Tips:</span> hexo的语法规定 <font size=4 face='微软雅黑' color="#1f87dd" style="font-weight:700;" class="nano-pointer"> : </font>后面
      <font size=4 face='微软雅黑' color="#1f87dd" style="font-weight:700;" class="nano-pointer">必须有一个空格</font>
    </div>
    <hr />
  </li>
  <li>
    <div >配置SSH Key 到GitHub</div>
    <div>
      <div>在Git Bash中输入: <span class="nano-pointer">ssh-keygen -t rsa -C "你的github邮箱号" </span> </div>
      <div>之后按三下回车出现以下内容</div>
      <img  src="../../img/ssh-key-1.png" />
    </div>
    <hr />
    <div>
      <div>找到.ssh文件夹，并打开其中的id_rsa.pub文件，复制里面的内容</div>
      <img  src="../../img/ssh-key-2.png" />
    </div>
    <hr />
    <div>
      <div>之后按下面图片步骤执行</div>
      <img  src="../../img/ssh-key-3.png" />
      <hr/>
      <img  src="../../img/ssh-key-4.png" />
       <hr/>
      <img  src="../../img/ssh-key-5.png" />
      <hr/>
      <img  src="../../img/ssh-key-6.png" />
      <hr/>
      <img  src="../../img/ssh-key-7.png" />
      <hr/>
      <div>此时在git bush中输入 <span class="nano-pointer">ssh -T git@github.com<span></div>
      <img  src="../../img/ssh-key-8.png" />
      <div class="nano-success">
      <img src="../../img/success-new.png" />
    如果出现了以上语句,则说明设置成功~</div>
    </div>
    <hr />
  </li>
   <li>
    <div >推送本地hexo 到GitHub</div>
    <div>
      <div>在Git Bash中设置用户信息:</div>
      <img src="../../img/hexo-to-push-1.png" />
      <hr />
      <div>编辑根目录下_config.yml文件,查找并切换到url字段位置,如图进行编辑:</div>
      <img src="../../img/hexo-to-push-2.png" />
      <div class="nano-tips"><span>Tips:</span>  <font size=4 face='微软雅黑' color="#1f87dd" style="font-weight:700;" class="nano-pointer"> 配置之后,初次上传就可以有样式了~ </font>
      </div>
      <hr />
    </div>
  </li>
</ul> 

## 搭建完成
<div class="flex-start nano-flex-start-align-end "> 
  <img src="../../img/rocket-succes.png" />
  <font size=5 face='微软雅黑' color="red" style="font-weight:700;"> last-step </font>
</div>
<ul class="nano-ul-flex">
  <li>
    输入 <span class="nano-pointer">hexo d</span> 指令推送到远端
    <img src="../../img/hexo-to-push-5.png">
    <div class="nano-tips"><span>Tips:</span>  <font size=4 face='微软雅黑' color="#1f87dd" style="font-weight:700;" class="nano-pointer"> 网络原因可能会推送不成功,多试几下就好了~ </font>
    </div>
    <hr />
  </li>
   <li>
    推送成功!
    <img src="../../img/hexo-to-push-3.png">
    <hr />
    <img src="../../img/hexo-to-push-7.jpg">
     <div class="nano-tips"><span>Tips:</span>  <font size=4 face='微软雅黑' color="#1f87dd" style="font-weight:700;" class="nano-pointer"> 因为picGo一直推不上去pc端的界面截图,所以展示了移动端的效果~ </font>
    </div>
     <hr />
  </li>
  <div class="nano-success">
    <img src="../../img/success-new.png" />
    这样就完成了博客的搭建与上传~</div>
</ul> 

## 最后の一些话
- 附上一些其它常用指令 <br/>
 <img src="../../img/instruct-hexo.png" />

- 其它念叨 <br/>
  - 之后也会陆续推出使用picgo搭配gitee做的图床教程,主要是为了减少静态资源的体积,本文的所有图片均来自gitee创建的图床~
  - 一开始不用gitee而选择github的原因是因为gitee的pages服务需要人工审核,审了我蛮久的,github不需要审核,就是需要科学上网,所以gitee也是可以做博客的,有兴趣的同学可以自己尝试一下~
  - hexo还有主题这些,后面也会出一些教程,毕竟我也才开始弄hexo,也不是很会,可能只会写一些很浅显的东西- -
  - 纪念第一篇博文,完结撒花,我去推了 2021-11-26
