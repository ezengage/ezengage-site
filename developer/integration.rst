如何将 ezEngage 集成到网站中?
=================================
如果你的站点并不是使用通用的CMS系统而是自己开发的, 你可以通过API 将ezEngage 集成到你的系统中。

创建并配置ezEngage应用
-------------------------
如果你还没有注册 `ezEngage <http://ezengage.com/signup/>`_ , 请先注册并 :ref:`创建一个ezEngage 应用 <create-ezengage-app>` 。

在我们支持 :ref:`供应商列表<provider-list>` 中选择一个或多个，并做对应的配置。

请记录下你的应用的 `App ID`, `App Domain`, `App Key`, 在下面的集成过程中将需要使用它们。

嵌入ezEngage登录控件
-------------------------
在你的网站的合适的地方，比如说你网站本身的登录页面, 加入下面的HTML代码。

.. Note::

   在将代码复制到你的网页中前，你必须要将ezengage_app_domain 配置项的值替换成你的app domain.

:: 

  <div id="ezc-login-widget-container"></div>
  <script type="text/javascript">
    /* * * CONFIGURATION VARIABLES: EDIT BEFORE PASTING INTO YOUR WEBPAGE * * */
    var ezengage_app_domain = 'example'; // required: replace example with your ezengage app domain
    var ezengage_token_cb = 'http://example.com/ezengage_token/'; //required: replace it with your actuall token url

    // The following are highly recommended additional parameters. Remove the slashes in front to use.
    // var ezengage_widget_style = 'connect';
    // var ezengage_widget_width = '400';
    // var ezengage_widget_height = '250';

    /* * * DON'T EDIT BELOW THIS LINE * * */
    (function() {
        var ezc = document.createElement('script'); ezc.type = 'text/javascript'; ezc.async = true;
        ezc.src = 'http://' + ezengage_app_domain + '.ezengage.net/embed.js';
        (document.getElementsByTagName('head')[0] || document.getElementsByTagName('body')[0]).appendChild(ezc);
    })();
  </script>


token处理
--------------------------

在上面的嵌入代码中用到了 `ezengage_token_cb` , 这个是在你的网站上的一个页面的URL。
通过ezEngage 平台登录完成后，ezEngage 会通过 `POST` 方式发送一个 `token` 到该页面。
页面从 `POST` 请求中分析出 `token`, 然后使用该 `token` 发送请求到 ezEngage 的 RESTful API, 来获取用户用户。


