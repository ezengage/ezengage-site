.. how to config sohuweibo provider

*********************
搜狐微博配置指南
*********************

为了让你的站点支持使用搜狐微博账号登录，你需要创建一个搜狐微博应用,　然后将应用的信息在填到ezEngage后台。

创建搜狐微博应用
=================================

打开搜狐微博开放平台
--------------------------
请通过浏览器访问 `搜狐微博开放平台 <http://open.t.sohu.com/>`_

登录搜狐微博账号
---------------------------
 如果你还没有登录, 请使用你的搜狐微博账号登录。

.. image:: https://img.skitch.com/20110516-bim1myk9a5q8r8c9818h3ixcbp.jpg

创建应用
--------------------------
在首页点击 *创建我的应用* 或者在我的应用页面点击 *创建应用*, 出现新应用表单。

.. image:: https://img.skitch.com/20110516-m2r7xabqjc37pq4t3fdrjfb8k8.jpg

资料填写

* 应用名称: 填入你的网站名称
* 应用地址: 填入你的网站地址
* 图标,公司或组织名称,应用描述,按实填写就可以了
* 应用分类随便选择一个（比如合作网站)
* 应用类型选择浏览器
* Callback URL

    * 如果你还没有创建ezEngage 应用，请 :ref:`创建一个ezEngage 应用 <create-ezengage-app>` , 并记录下来的你 `App Domain` 。
    * 如果你已经创建了ezEngage 应用，请 :ref:`找到应用信息 <find-ezengage-app-info>`, 并记录下 `App Domain` 。

    假设你的 `App Domain` 是 `exampleappdomain`, 就将 `http://exampleappdomain.ezengage.net` 填入Callback URL项目内。 

相关内容填写完毕后，请点击 *创建应用* 按钮进行保存信息。

获得Consumer Key 和 Consumer Secret
-----------------------------------------
应用创建完成后，会在 *我的应用页面* 列出，点击应用的图标, 进入应用状态页面，点击右侧的应用详细信息。
在这个页面你可以看到应用的Consumer Key 和Consumer Secret 。

.. image:: https://img.skitch.com/20110516-bcxddtbw2xmpyhn8pcs6197eef.jpg
.. image:: https://img.skitch.com/20110516-gpjjqrcicjwdn73rhdbskdhtm8.jpg
.. image:: https://img.skitch.com/20110516-d5yq785pdxsij5kjyg69ixk99y.jpg

请将Consumer Key 和Consumer Secret 记录下来, 你将需要在ezEngage管理后台配置时使用这个信息。

配置ezEngage App 的搜狐微博设置
=================================
在上面的步骤中，你已经创建了一个搜狐微博应用，并把 `Consumer Key`, `Consumer Secret` 记录下来了。

请访问 `ezEngage管理后台 <http://ezengage.com/dashboard/>`_ ，选择修改应用配置, 修改搜狐微博配置，在弹出窗口中将上面两个值填入表单并保存。

.. image:: https://img.skitch.com/20110516-rbhmf5irb7fg83mgpxwb37u3yt.jpg

参考 :ref:`how-to-config-ezengage-app` 

