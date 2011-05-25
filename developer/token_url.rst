服务器端集成
=================

.. _token-url:

Token URL
-----------------------

`token_url` 是你的网站是的的一个处理程序。取决你使用的编程语言，它可能是一个PHP页面，CGI脚本或者JSP脚本。
在登录完成后ezEngage 会将用户的认证信息发送到该URL, 该脚本接受认证信息，并发送请求到 ezEngage 的 RESTful API, 来获取用户档案。 

一般来说，可以将该脚本放在你的网站的根目录下,并起类似 *ezengage_token.php* 这样的名字。

Token URL 处理逻辑
----------------------

具体来说，用户在ezEngage 完成认证过程后，一个POST 请求将会发送到 `token_url` ，请求包含一个参数 `token` ,
在你的Token URL 处理程序中，你需要做下面的几件事情

1. 从 *POST* 请求中提取出 `token` 参数
2. 使用该token 访问 :ref:`Get Profile API <api-get-profile>` 来获得登录用户的信息 (ezEngage Profile)。
3. (可选) 将用户信息(ezEngage Profile)保存到你的数据库中。
4. 一般来说你的站点会有自己的用户数据库, 你应该建立一个你的站点用户和ezEngage Profile 之间的关联关系。
   
   * 如果发现获得 ezEngage Profile 没有和任何用户关联，你可以自动创建一个本地用户(或者要求用户完成你的站点的注册)，然后将其和 ezEngage Profile 关联起来。
   * 如果说该ezEngage Profile 已经和你的站点的用户管理起来了，那就登录对应的用户。　

.. note:: token 是一次性的，使用token 请求 :ref:`Get Profile API <api-get-profile>` 一次后该token 就失效了。

.. note:: ezEngage Profile 中的 `identity` 可以唯一标识一个用户, 也就是说如果两次获得的用户信息中 `identity` 字段是一样的，那么表示两次登录的是同一个用户。


示例代码
------------------------
在我们的GitHub 代码仓库里面可以找到 `token_url` 的示例代码。

`ezEngage 示例代码仓库 <https://github.com/ezengage/ezengage-sample-code/>`_ 。

目前只包含 php 的代码示例。

