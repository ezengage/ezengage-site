服务器端集成
=================

.. _token-url:

token_url
-----------------------

`token_url` 是你的网站是的的一个处理程序。取决你使用的编程语言，它可能是一个PHP页面，CGI脚本或者JSP脚本。
在登录完成后ezEngage 会将用户的认证信息发送到该URL, 该脚本接受认证信息，并发送请求到 ezEngage 的 RESTful API, 来获取用户档案。 

一般来说，可以将该脚本放在你的网站的根目录下,并起类似 **ezengage_token.php** 的这样的名字。

具体来说，用户在ezEngage 登录完成后，一个POST 请求将会发送到 `token_url` ，请求包含一个参数 `token` , 在处理程序中，你应该提取中 `token`
参数，然后使用该token 访问 `profile` API 来获得登录用户的信息。

.. note::
 
  token 是一次性的，使用token 请求 `profile` API一次后该token 就失效了。


示例代码
------------------------
在我们的GitHub 代码仓库里面可以找到 `token_url` 的示例代码。

`ezEngage 示例代码仓库 <https://github.com/ezengage/ezengage-sample-code/>`_ 。

目前只包含 php 的代码示例。

