.. how to config sinaweibo provider

*********************
网易微博配置指南
*********************

为了让你的站点支持使用网易微博账号登录，你需要创建一个网易微博应用,　然后将应用的信息在填到ezEngage后台。

创建网易微博应用
=================================

打开网易微博开放平台
--------------------------
请通过浏览器访问 `网易微博开放平台 <http://open.t.163.com/>`_

进入我的应用
---------------------------
请点击我的应用, 如果你还没有登录, 请使用你的网易微博账号登录。

.. image:: https://img.skitch.com/20110516-18g7aibcyyk314ehpqque82twk.jpg

创建应用
--------------------------
在我的应用页面点击 *创建新应用*,出现新应用表单。

.. image:: https://img.skitch.com/20110516-rfqqpj7j65j2a9m6xcfmfn5e3q.jpg

资料填写

* 应用名称: 填入你的网站名称
* 应用网站: 填入你的网站地址
* 图标,描述,开发者名称按实填写就可以了
* 应用分类随便选择一个（比如其他客户端)

相关内容填写完毕后，请点击 *提交* 按钮进行保存信息。

获得Consumer Key 和 Consumer Secret
-----------------------------------------
应用创建完成后，会在 *应用列表* 列出，点击应用的图标, 进入应用详细信息页面。
在这个页面你可以看到应用的Consumer Key 和Consumer Secret 。

.. image:: https://img.skitch.com/20110516-d7huuib9tic1hgk683de33fw3b.jpg 
.. image:: https://img.skitch.com/20110516-n13wwmr65j1h6wkyqfrp2f1t74.jpg

请将Consumer Key 和Consumer Secret 记录下来, 你将需要在ezEngage管理后台配置时使用这个信息。


配置ezEngage App 的网易微博设置
=================================
在上面的步骤中，你已经创建了一个网易微博应用，并把 `Consumer Key`, `Consumer Secret` 记录下来了。

请访问 `ezEngage管理后台 <http://ezengage.com/dashboard/>`_ ，选择修改应用配置, 修改网易微博配置，在弹出窗口中将上面两个值填入表单并保存。

.. image:: https://img.skitch.com/20110516-xfftarxw1b9tu6ka9bcrree2qd.jpg

参考 :ref:`how-to-config-ezengage-app` 

