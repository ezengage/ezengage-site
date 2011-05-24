登录Widget
====================
ezEngage *登录Widget* 可以在你的网站上嵌入ezEngage的登录界面，
让用户可以直接使用已有的社交网络账号登录到你的站点。

Widget中显示的 :ref:`供应商列表<provider-list>` 可以在ezEngage管理中心配置。


在网站上加入登录Widget
-----------------------------


创建并配置ezEngage应用
~~~~~~~~~~~~~~~~~~~~~~~~
如果你还没有注册 `ezEngage <http://ezengage.com/signup/>`_ , 请先注册并 :ref:`创建一个ezEngage 应用 <create-ezengage-app>` 。

在我们支持 :ref:`供应商列表<provider-list>` 中选择一个或多个，并做对应的配置。

请记录下你的应用的 `App ID`, `App Domain`, `App Key`, 在下面的步骤中将需要使用它们。

嵌入Widget
~~~~~~~~~~~~~~~~~~~~~~~
我们通过JavaScript脚本来嵌入ezEngage 登录Widget。

在你的网站的合适的地方，比如说网站的登录和注册页面, 加入下面的HTML代码。

.. Note::

   在将代码复制到你的网页中前，你必须要将ezengage_app_domain 配置项的值替换成你的App Domain。

.. Note::

   ezengage_token_cb 的值需要修改成你的 :ref:`token_cb<token_cb>` 的完整URL。不过如果你只是希望预览一下嵌入登录Widget的网页样式，那可以先不改。

:: 

  <div id="ezc-login-widget-container"></div>
  <script type="text/javascript">
    /* * * CONFIGURATION VARIABLES: EDIT BEFORE PASTING INTO YOUR WEBPAGE * * */
    var ezengage_app_domain = 'example'; // required: replace example with your ezengage app domain
    var ezengage_token_cb = 'http://example.com/ezengage_token/'; //required: replace it with your actuall token url

    // The following are additional parameters. Remove the slashes in front to use.
    // var ezengage_widget_style = 'normal';
    // var ezengage_widget_width = '350';
    // var ezengage_widget_height = '190';
    // var ezengage_container_id = 'ezc-login-widget-container';

    /* * * DON'T EDIT BELOW THIS LINE * * */
    (function() {
        var ezc = document.createElement('script'); ezc.type = 'text/javascript'; ezc.async = true;
        ezc.src = 'http://' + ezengage_app_domain + '.ezengage.net/login/embed.js';
        (document.getElementsByTagName('head')[0] || document.getElementsByTagName('body')[0]).appendChild(ezc);
    })();
  </script>

网页加入这一段代码后，脚本将会在 `<div id="ezc-login-widget-container></div>` 这个div 中嵌入登录Widget。
你可以按你的需求调整这个div在你的网页中位置。

比如说下面的代码就嵌入了ezEngage 的 demo app 的登录控件。

:: 

  <div id="ezc-login-widget-container"></div>
  <script type="text/javascript">
    /* * * CONFIGURATION VARIABLES: EDIT BEFORE PASTING INTO YOUR WEBPAGE * * */
    var ezengage_app_domain = 'demo'; // required: replace example with your ezengage app domain
    var ezengage_token_cb = 'http://demo.ezengage.com/token.php'; //required: replace it with your actuall token url

    /* * * DON'T EDIT BELOW THIS LINE * * */
    (function() {
        var ezc = document.createElement('script'); ezc.type = 'text/javascript'; ezc.async = true;
        ezc.src = 'http://' + ezengage_app_domain + '.ezengage.net/login/embed.js';
        (document.getElementsByTagName('head')[0] || document.getElementsByTagName('body')[0]).appendChild(ezc);
    })();
  </script>


登录Widget 预览

.. raw:: html

  <div id="ezc-login-widget-container"></div>
  <script type="text/javascript">
    var ezengage_app_domain = 'demo'; // required: replace example with your ezengage app domain
    var ezengage_token_cb = 'http://demo.ezengage.com/token.php'; //required: replace it with your actuall token url

    (function() {
        var ezc = document.createElement('script'); ezc.type = 'text/javascript'; ezc.async = true;
        ezc.src = 'http://' + ezengage_app_domain + '.ezengage.net/login/embed.js';
        (document.getElementsByTagName('head')[0] || document.getElementsByTagName('body')[0]).appendChild(ezc);
    })();
  </script>


Widget配置参数
---------------------
Widget 共有6个参数，其中2个是必需的参数，其余4个是可选。

========================  ===========   ======================================================================
参数名称                  是否必需      值说明
========================  ===========   ======================================================================
ezengage_app_domain       是            你的ezEngage App Domain
ezengage_token_cb         是            你的token_cb 的完整URL
ezengage_widget_style     否            Widget 风格,默认normal。可选值normal, medium, small, tiny 。
ezengage_widget_width     否            Widget 的宽度
ezengage_widget_height    否            Widget 的高度
ezengage_container_id     否            嵌入Widget 的容器Dom元素的ID,默认是 *ezc-login-widget-container* 。
========================  ===========   ======================================================================
