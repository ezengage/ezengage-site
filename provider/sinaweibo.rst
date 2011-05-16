.. how to config sinaweibo provider

*********************
新浪微博配置指南
*********************

为了让你的站点支持使用新浪微博账号登录，你需要创建一个新浪微博应用,　然后将应用的信息在填到ezEngage后台。

创建新浪微博应用
=================================
.. note::
   该文档部分内容参考了 `新浪微博开放平台新手指南 <http://open.t.sina.com.cn/wiki/index.php/%E6%96%B0%E6%89%8B%E6%8C%87%E5%8D%97>`_

打开新浪微博开放平台
--------------------------
请通过浏览器访问 `新浪微博开发平台 <http://open.t.sina.com.cn/>`_

登录新浪微博账号
---------------------------
请使用你的新浪微博账号登录。

.. image:: http://www.s2forum.org/wikipic/lc-denglu.png

设置开发者信息
--------------------------
在开放平台首页右上方点击 *我的应用* , 如何你还没有设置开发者信息，会打开 *编辑开发者信息* 页面,请填写完整并保存设置.

.. image:: https://img.skitch.com/20110516-bwpetxegjfebpj1rfb27jtmh4d.jpg


创建应用
--------------------------
在开放平台页面右侧点击 *创建应用*

.. image:: http://www.s2forum.org/wikipic/lc-chuangjian.png
资料填写

* 图标: 使用你的网站的Logo 即可.
* 应用名称: 填入你的站点的名称
* 应用地址: 填入你的站点的地址
* 应用介绍: 填入你的站点的介绍
* 域名绑定选择 *否*
* 应用分类,标签等随便选择一个就可以了

.. image:: https://img.skitch.com/20110516-eg1rs8yt8yp6cfjgy3dpud69an.jpg

相关内容填写完毕后，请点击 *创建* 按钮进行保存信息。

获得App Key 和 App Secret
-----------------------------
应用创建完成后，将会进入应用状态页面。在这个页面你可以看到应用的App Key 和App Secret .

.. image:: https://img.skitch.com/20110516-kbdtq4pt99pe7rufrxnbw1utpc.jpg

请将App Key 和App Secret 记录下来, 你将需要在ezEngage管理后台配置时使用这个信息。

应用审核
----------------
关于应用的审核请参考新浪的 `微博开放平台应用审核规范 <http://open.t.sina.com.cn/wiki/index.php/%E5%BE%AE%E5%8D%9A%E5%BC%80%E6%94%BE%E5%B9%B3%E5%8F%B0%E5%BA%94%E7%94%A8%E5%AE%A1%E6%A0%B8%E8%A7%84%E8%8C%83/>`_ .

配置ezEngage App 的新浪微博设置
=================================
在上面的步骤中，你已经创建了一个新浪微博应用，并把 `APP Key`, `APP Secret` 记录下来了。

请访问 `ezEngage管理后台 <http://ezengage.com/dashboard/>`_ ，选择修改应用配置, 修改新浪微博配置，在弹出窗口中将上面两个值填入表单并保存。

.. image:: https://img.skitch.com/20110516-b32ndg9tess2nki19arrmc1e8c.jpg

参考 :ref:`how-to-config-ezengage-app` 

