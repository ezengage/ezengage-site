*********************
WordPress 系统集成
*********************

创建并配置ezEngage应用
=========================
如果你还没有注册 `ezEngage <http://ezengage.com/signup/>`_ , 请先注册并 :ref:`创建一个ezEngage 应用 <create-ezengage-app>` 。

在我们支持 :ref:`供应商列表<provider-list>` 中选择一个或多个，并做对应的配置。

安装ezEngage WordPress 插件
=================================
系统要求
----------
插件目前只支持 `WordPress` 3.0 以上版本。
PHP环境需要支持 `fsockopen` 函数。

后台安装
----------
你可以直接在Wordpress 后台搜索 ezengage 插件直接安装。

手工安装
-----------
你也可以手工下载并安装。

1. 访问 http://wordpress.org/extend/plugin/ezengage 下载最新版本。　
2. 上传 `ezengage` 目录和其中的内容到你的 `/wp-content/plugins/` 目录。
3. 通过 `插件` 菜单激活 ezEngage 插件。

配置
----------
1. 找到你在ezEngage网站创建的应用的App Domain, APP Id 和 App Key。(:ref:`find-ezengage-app-info`)
2. 访问 `设置--> ezEngage` 打开ezEngage 配置页面, 将App Domain, App Id, App Key 填入表单，勾选启用ezEngage并点击保存。
   
   .. image:: http://s3-us-west-1.amazonaws.com/media.ezengage.com/yumpweb/20110515143119-g/img/wordpress-plugin-config.png

到这里，插件已经安装成功了。用户可以使用社交网络的帐号登录你的站点了。
 
使用方法
=============

社会化登录
--------------
安装完成，在登录页,注册页,文章评论区域会出现ezEngage 登录控件。
用户可以直接它们的社交网络和微博账号登录到你的站点。

  .. image:: http://s3-us-west-1.amazonaws.com/media.ezengage.com/yumpweb/20110515143119-g/img/wordpress-plugin-login.png
  .. image:: http://s3-us-west-1.amazonaws.com/media.ezengage.com/yumpweb/20110515143119-g/img/wordpress-plugin-comment.png

用户在从第三方登录完成后,系统会自动为他创建一个WordPress的用户,然后登录。需要注意的用户的Email是系统自动生成的假Email。

多账户绑定和管理
-------------------
插件支持一个WordPress用户绑定多个社交网络账号，比如说同时绑定新浪微博微博和腾讯微博账号到同一个WordPress账号。

用户可以访问 `用户 --> 第三方帐号`, 绑定多个帐号或者解除绑定。以及设置是否同步文章到绑定的帐号上。 

  .. image:: http://s3-us-west-1.amazonaws.com/media.ezengage.com/yumpweb/20110515143119-g/img/wordpress-plugin-accounts.png


高级功能
=============

你可以在 `设置 --> EzEngage` 界面修改登录界面的样式。
可选的有 "链接", "小图标" , "大图标"，以及"不显示，我要自己修改模版"。 如果你选择自己修改模版，你可以在模版中插入下面的代码显示一个ezEngage 登录界面.

 :: 

   <?php ezengage_login_ui('small',  true); ?>

第一个参数的可选值有 'link', 'small', 'normal' 分别对应"链接", "小图标", "大图标"。第二个参数表示登录完成后是否返回当前页面， 可选值为 true, false. 另外如果你希望只在用户没有登录的是否才显示这个界面。 请使用如下代码

 :: 
  
   <?php if($user_ID > 0) { ezengage_login_ui('small', true); } ?>



