*********************
Discuz!X 系统集成
*********************

创建并配置ezEngage应用
=========================
如果你还没有注册 `ezEngage <http://ezengage.com/signup/>`_ , 请先注册并 :ref:`创建一个ezEngage 应用 <create-ezengage-app>` 。

在我们支持 :ref:`供应商列表<provider-list>` 中选择一个或多个，并做对应的配置。

安装ezEngage Discuz!X 插件
=================================
系统要求
----------
插件目前只支持DiscuzX! 1.5 系统。
PHP环境需要支持 `fsockopen` 函数。

下载
----------
插件的最新版本版本为0.2.3, 下载地址为 

https://github.com/ezengage/discuz-ezengage/downloads/ezengage-for-discuzx-0.2.3.zip

安装
----------
1. 从上面的地址下载最新版本的插件。
2. 解压下载的文件，将upload目录下的内容上传你的Discuz X 安装目录。
3. 访问Discuz X 后台, 打开"插件" -> "安装新插件" ，安装ezEngage (注意选择和你的站点编码匹配的版本)。

配置
----------
1. 找到你在ezEngage网站创建的应用的App Domain, APP Id 和 App Key。(:ref:`find-ezengage-app-info`)
2. 访问"插件"点击"ezEngage", 然后点击"配置", 将App Domain, App Id, App Key 填入参数设置。
   
   .. image:: http://s3-us-west-1.amazonaws.com/media.ezengage.com/yumpweb/20110515143119-g/img/discuzx-plugin-config.png

3. 如果你希望用户能够不注册直接使用社交网络帐号登录，请启用自动注册。
4. 返回"插件"启用ezEngage 。
5. 请检查你网站URL设置("全局"->"站点信息"->网站URL)设置是正确的。
   该地址必须以'/'结尾,指向你的网站首页。
   比如说你的网站是 `http://bbs.example.com/` 那就在网站URL 里面填入 `http://bbs.example.com/` 。
   
   .. image:: http://s3-us-west-1.amazonaws.com/media.ezengage.com/yumpweb/20110515143119-g/img/discuzx-plugin-site-url.png

到这里，插件已经安装成功了。用户可以使用社交网络的帐号登录你的站点了。
 
使用方法
=============

社会化登录
--------------
安装完成，在登录页,注册页和页面头部登录框左边会出现ezEngage 登录控件。
用户可以直接它们的社交网络和微博账号登录到你的站点。

  ..image:: http://s3-us-west-1.amazonaws.com/media.ezengage.com/yumpweb/20110515143119-g/img/discuzx-plugin-top.png
  ..image:: http://s3-us-west-1.amazonaws.com/media.ezengage.com/yumpweb/20110515143119-g/img/discuzx-plugin-login.png
  ..image:: http://s3-us-west-1.amazonaws.com/media.ezengage.com/yumpweb/20110515143119-g/img/discuzx-plugin-register.png

多账户绑定和管理
-------------------
插件支持一个Discuz用户绑定多个社交网络账号，比如说同时绑定新浪微博微博和腾讯微博账号到同一个Discuz账号。
用户访问"设置"->"我绑定的账号"，来绑定多个帐号或者解除绑定。

  .. image:: http://s3-us-west-1.amazonaws.com/media.ezengage.com/yumpweb/20110515143119-g/img/discuzx-plugin-accounts.png


用户活动同步
-------------------
默认情况下，主题贴,日志,分享,记录会被同步到绑定的帐号上。

比如说用户A绑定了新浪微博账号B, 那么A在在论坛发了一条贴后，系统会使用新浪微博账号B也发布这个帖子，并带有到论坛该帖子的链接。

用户可以在 *我绑定的帐号* 页面修改同步哪些内容。


