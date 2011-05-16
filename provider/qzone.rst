.. how to config tencentweibo provider
*********************
QQ配置指南
*********************

为了让你的站点支持使用QQ账号登录，你需要创建一个腾讯社区开放平台应用, 然后将应用的信息在填到ezEngage后台。

创建QQ登录应用
=================================

打开腾讯社区开放平台
--------------------------
请通过浏览器访问 `腾讯社区开发平台的QQ登录页面 <http://connect.opensns.qq.com/>`_

登录QQ账号
---------------------------
请使用你的QQ账号登录。

.. image:: https://img.skitch.com/20110516-mefc98hptisy6ccn7167c68634.jpg

申请网站QQ登录
--------------------------

点击网站申请

.. image:: https://img.skitch.com/20110428-1d15kjfwiqrjwg8nyhp4uptf6s.png
出现申请接入页面，表单有两个主要部分网站信息和OAuth 参数。

网站信息
^^^^^^^^^^^^^^^
网站信息部分按你的实际情况填写网站名称，网站域名, ICP证就可以了。
域名验证只要按页面的提示将文件上传到你的服务器根目录就可以了。

OAuth 参数
^^^^^^^^^^^^^^^

.. image:: https://img.skitch.com/20110428-g7udfypggepnkyd7njhxj844ir.png

1. 网站Logo 请上传你的网站的Logo 。
2. 回调地址域名

   * 如果你还没有创建ezEngage 应用，请 :ref:`创建一个ezEngage 应用 <create-ezengage-app>` , 并记录下来的你 `App Domain` 。
   * 如果你已经创建了ezEngage 应用，请 :ref:`找到应用信息 <find-ezengage-app-info>`, 并记录下 `App Domain` 。

   假设你的 `App Domain` 是 `exampleappdomain`, 就将 `http://exampleappdomain.ezengage.net` 填入 *回调地址域名* 。

3. 登录页地址可以设置为你的网站首页，或者设置成和回调域名地址一样。

相关内容填写完毕后，请点击 *提交申请* 按钮保存信息。

获得App ID 和 App Key
-----------------------------
在 *我的申请* 页面，会列出你提交的申请，页面上可以找到应用的 `APP Id` 和 `APP Key` 。

.. image:: https://img.skitch.com/20110516-e4wpmdxnmd661f54p3jbujdh3.jpg

请将 `App ID` 和 `App Key` 记录下来, 你将需要在ezEngage管理后台配置时使用这个信息。

配置ezEngage App 的QQ设置
=================================
在上面的步骤中，你已经创建了一个QQ登录应用，并把 `APP ID`, `APP Key` 记录下来了。

请访问 `ezEngage管理后台 <http://ezengage.com/dashboard/>`_ ，选择修改应用配置, 修改QQ配置，在弹出窗口中将上面两个值填入表单并保存。

.. image:: https://img.skitch.com/20110516-8mq72d1iymtkp5jbdf1d5ea895.jpg

参考 :ref:`how-to-config-ezengage-app` 

