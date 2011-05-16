*********************
人人网配置指南
*********************

为了让你的站点支持使用人人网账号登录，你需要创建一个人人网应用,　然后将应用的信息在填到ezEngage后台。

创建人人网应用
=================================

打开人人网开放平台
--------------------------
请通过浏览器访问 `人人网开发平台 <http://dev.renren.com/>`_ 。
如果你还没有登录，请使用你的人人网账号登录。

创建应用
--------------------------
点击页面上的 *创建新应用* 按钮。

.. image:: https://img.skitch.com/20110516-8ae7di46pifwr3mp2nstnjwh39.jpg

填入应用名称, 应用名称可以使用你的站点的名称或域名, 阅读并同意协议，然后点击 *保存设置* 。

.. image:: https://img.skitch.com/20110516-jxdxcqf6b7k5mpcfuhkdcswp88.jpg

.. note::
   图中的 `ezengage-demo` 仅仅是一个示意，请不要使用这个名字。

获得应用API Key,Secret Key
-------------------------------
在创建完应用后，会进入 *应用基本信息设置* 页面。
在这个页面你可以找到应用的 `API Key` 和 `Secret Key` 。


.. image:: https://img.skitch.com/20110516-q93j312afxahx6hkdkxr68pqm3.jpg

如果你是之前创建的应用，请打开 *我的应用* ,　选择你之前创建的应用, 也可以找到 `API Key` 和 `Secret Key` 。

.. image:: https://img.skitch.com/20110516-8if4en6q27y5b72it3d7r3ux7b.jpg

请将 `API Key` 和 `Secret Key` 记录下来, 你将需要在ezEngage管理后台配置时使用这个信息。

.. _renren-set-website-info:

设置 *网站信息* 
-------------------

.. note::
   这个步骤很重要，如果不设置，用户是无法使用人人网账号登录的。

请打开 *我的应用* ,　选择你之前创建的应用, 点击 *编辑应用属性* 。

.. image:: https://img.skitch.com/20110516-mx7ab1c9hj7sfuqyxjpwdwu6tt.jpg

选择 *网站信息*, 将 `ezengage.net` 填入根域名中。

* 如果你还没有创建ezEngage 应用，请 :ref:`创建一个ezEngage 应用 <create-ezengage-app>` , 并记录下来的你 `App Domain` 。
* 如果你已经创建了ezEngage 应用，请 :ref:`找到应用信息 <find-ezengage-app-info>`, 并记录下 `App Domain` 。

假设你的 `App Domain` 是 `exampleappdomain`, 就将 `http://exampleappdomain.ezengage.net` 填入网站URL项目内。 

.. image:: http://s3-us-west-1.amazonaws.com/media.ezengage.com/yumpweb/20110515143119-g/photo/renren-config-domain-4.png

点击 *保存连接网站设置* 。


创建Feed模板(用于同步用户活动)
-------------------------------
如果你需要支持同步用户在你的站点的活动到人人网，你需要创建一个Feed模板。

创建流程请参考下面７张截图。

.. image:: http://s3-us-west-1.amazonaws.com/media.ezengage.com/yumpweb/20110515143119-g/photo/renren-edit-feed-template-1.jpg

.. image:: http://s3-us-west-1.amazonaws.com/media.ezengage.com/yumpweb/20110515143119-g/photo/renren-edit-feed-template-2.jpg

.. image:: http://s3-us-west-1.amazonaws.com/media.ezengage.com/yumpweb/20110515143119-g/photo/renren-edit-feed-template-3.jpg

.. image:: http://s3-us-west-1.amazonaws.com/media.ezengage.com/yumpweb/20110515143119-g/photo/renren-edit-feed-template-4.jpg

.. image:: http://s3-us-west-1.amazonaws.com/media.ezengage.com/yumpweb/20110515143119-g/photo/renren-edit-feed-template-5.jpg

.. image:: http://s3-us-west-1.amazonaws.com/media.ezengage.com/yumpweb/20110515143119-g/photo/renren-edit-feed-template-6.jpg

.. image:: http://s3-us-west-1.amazonaws.com/media.ezengage.com/yumpweb/20110515143119-g/photo/renren-copy-feed-template-id.jpg

将模版组ID记录下来。

配置ezEngage App 的人人网设置
=================================
在上面的步骤中，你已经创建了一个人人网应用和对应的Feed模板，并把 `API Key`, `Secret Key` 以及 `Feed 模版组ID` 记录下来了。

请访问 `ezEngage管理后台 <http://ezengage.com/dashboard/>`_ ，选择修改应用配置, 修改人人网配置，在弹出窗口中将上面三个值填入表单并保存。

.. image:: https://img.skitch.com/20110516-dpdpks5p9sgr77gr28u57wh4j4.jpg

参考 :ref:`how-to-config-ezengage-app` 

常见问题
=================================

登录时出现”通过人人网登录失败“
---------------------------------

如果提示 `redirect_uri_mismatch` , 请检查 :ref:`renren-set-website-info` 步骤的操作是否执行正确了。　

.. image:: https://img.skitch.com/20110516-djkfa7ssc8c5sw97tkrcn38j6m.jpg

消息没有同步到人人网
-------------------------------
人人网有session key 过期机制(一般是24小时), 如果你的网站上的用户A帮定了人人网账号，但是在24小时内没有通过人人网登录,
而是通过你的站点的用户名和密码登录的，那么用户的session key　将过期，用户的活动将无法同步到人人网, 直到用户通过人人网账号登录你的站点。

