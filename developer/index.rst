ezEngage 开发者指南
=====================

这份文档是提供给希望在自己开发的网站中集成ezEngage服务的用户阅读的。

通过使用ezEngage 提供的RESTful API和Widget, 你的站点可以很方便的接入ezEngage系统，让你的网站支持使用多个社交网络和微博(包括新浪微博，人人网，腾讯微博, QQ, 豆瓣等)的账号登录到你的站点，并推送用户活动到这些社交网络。　


网站集成教程
---------------

下面的教程会指导你如何在网站上集成ezEngage 服务。

创建并配置ezEngage应用
^^^^^^^^^^^^^^^^^^^^^^^^^
同使用插件一样，你需要注册ezEngage 账号，并创建和配置一个应用。

如果你还没有注册 `ezEngage <http://ezengage.com/signup/>`_ , 请先注册并 :ref:`创建一个ezEngage 应用 <create-ezengage-app>` 。

在我们支持 :ref:`供应商列表<provider-list>` 中选择一个或多个，并做对应的配置。

:ref:`找到你创建的应用的信息 <find-ezengage-app-info>`, 并记录下你的应用的 `App ID`, `App Domain`, `App Key`, 在下面的集成过程中将需要使用它们。



在网站的合适位置嵌入登录Widget
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
在你网站的合适位置嵌入登录Widget.
详细请阅读 :ref:`embed-login-widget` 。

.. note:: 这个步骤需要用到的 Token URL 还没有实现，你可以先随便写一个，看一下Widget的效果。

实现Token Url处理逻辑
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
这个步骤需要你编写代码，实现Token URL 的处理逻辑。　

详细请阅读 :ref:`token-url` 。

修改Widget 代码
^^^^^^^^^^^^^^^^^^^^^
假设你的网站的地址是 *http://www.example.com* , 你实现的 `Token URL` 的地址是 *http://www.example.com/ezengage_token.php* 。
那么请将你的Widget 的代码中的 **ezengage_token_cb** 变量值修改为 *http://www.example.com/ezengage_token.php* 。

.. note:: 上面使用的地址仅仅是示例，请将其替换成你的 **实际** 的Token URL 的地址。

修改完 **ezengage_token_cb** 后你的站点就完成ezEngage 接入了。


推送用户活动到社交网络
^^^^^^^^^^^^^^^^^^^^^^^^
你可以推送用户的活动到社交网络, 比如说用户的发帖，购买，评论等等。　

你可以调用 :ref:`api-update-status` 来推送消息。

1. 从你的数据中找出用户对应的 ezEngage `Identity` , 这个值作为参数 *identity* 。
2. 将你需要推送的内容组成一个字符串(UTF-8编码), 这个值作为参数 *status* 。
3. 使用参数 *identity* , 参数 *status* 以及你的 ezEngage APP Key 调用 Update Status API 。

