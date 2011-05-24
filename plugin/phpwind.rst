*********************
phpwind 系统集成
*********************

创建并配置ezEngage应用
=========================
如果你还没有注册 `ezEngage <http://ezengage.com/signup/>`_ , 请先注册并 :ref:`创建一个ezEngage 应用 <create-ezengage-app>` 。

在我们支持 :ref:`供应商列表<provider-list>` 中选择一个或多个，并做对应的配置。

安装ezEngage phpwind 插件
=================================
系统要求
----------
插件目前只支持phpwind 8.5 系统。
PHP环境需要支持 `fsockopen` 函数。

下载
----------
插件的最新版本版本为0.1.4, 下载地址为 

https://github.com/ezengage/pw-ezengage/downloads/ezengage-for-phpwind-0.1.4.zip

安装
----------
1. 从上面的地址下载最新版本的插件。
2. 解压下载的文件，将upload目录下的内容上传你的phpwind安装目录。

   .. note:: 注意upload 目录下面的 **hack** 目录和 **ezengage.php** 文件 **都** 需要上传。

3. 访问PHPWind后台, 打开"应用" -> "插件中心" ，安装ezEngage。

配置
----------
1. 找到你在ezEngage网站创建的应用的App Domain, APP Id 和 App Key。(:ref:`find-ezengage-app-info`)
2. 访问"插件中心", 点击 "ezEngage" 的设置, 将App Domain, App Id, App Key 填入参数设置, 并选择 **启用** 插件。
   
   .. image:: http://s3-us-west-1.amazonaws.com/media.ezengage.com/yumpweb/20110515143119-g/photo/support/phpwind-config.png

3. 如果你希望用户能够不注册直接使用社交网络帐号登录，请启用自动注册。
4. 按照提示访问"全局 ->导航设置 –>顶部右侧导航", 设置菜单。 

   .. image:: http://s3-us-west-1.amazonaws.com/media.ezengage.com/yumpweb/20110515143119-g/photo/support/phpwind-config-menu.png

到这里，插件已经安装好了。但是我们还需要修改几个PHPWind系统的文件，插件才能正常工作。

修改phpwind 系统文件
-----------------------
.. note:: 下面提到的文件路径都是相对于phpwind根目录。
    
修改 `post.php`
^^^^^^^^^^^^^^^^^
打开 `post.php` 在文件末尾找到下面的代码

::
   
   if ($action == "new") {
      require_once(R_P.'require/postnew.php');
   } elseif ($action == "reply" || $action == "quote") {
      require_once(R_P.'require/postreply.php');
   } elseif ($action == "modify") {
      require_once(R_P.'require/postmodify.php');
   } else {
      Showmsg('undefined_action');
   }

在这一段代码 **前面** 加入下面的代码

::

   //start ezengage hack 
   @require_once(R_P . 'hack/ezengage/sync.php');
   //end ezengage hack 

修改模版文件
^^^^^^^^^^^^^^^^^^^
打开 `template/wind/footer.html` , `template/wind/showmsg.html` 和 `mode/area/template/footer.html` 。
在这三个模版文件的 **最末尾**, 加入下面的代码

::

   <script type="text/javascript" src="ezengage.php?mod=js&scr=<?php echo SCR;?>"></script>


使用方法
=============

社会化登录
--------------
安装完成，在登录页,注册页和页面头部登录框左边会出现ezEngage 登录控件。
用户可以直接使用他们的社交网络和微博账号登录到你的站点。

.. image:: http://s3-us-west-1.amazonaws.com/media.ezengage.com/yumpweb/20110515143119-g/photo/support/phpwind-top-login.jpg

.. image:: http://s3-us-west-1.amazonaws.com/media.ezengage.com/yumpweb/20110515143119-g/photo/support/phpwind-login-widget.jpg


如果自动注册功能启用了，用户在从第三方登录完成后,系统会自动为他创建一个PHPWind的用户,然后登录,否则会要求用户完成站点的注册流程后绑定第三方账号。


多账户绑定和管理
-------------------
插件支持一个phpwind用户绑定多个社交网络账号，比如说同时绑定新浪微博微博和腾讯微博账号到同一个phpwind账号。
用户可以访问"我绑定的帐号", 绑定多个帐号或者解除绑定。

.. image:: http://s3-us-west-1.amazonaws.com/media.ezengage.com/yumpweb/20110515143119-g/photo/support/phpwind-my-accounts.jpg


用户活动同步
-------------------
默认情况下，主题贴会被同步到绑定的帐号上。

比如说用户A绑定了新浪微博账号B, 那么A在在论坛发了一条贴后，系统会使用新浪微博账号B也发布这个帖子，并带有到论坛该帖子的链接。

用户可以在 *我绑定的帐号* 页面修改同步那些内容。

