ezComment 评论系统
========================
ezComment 是一个评论系统，它用来给你的站点的内容加入评论功能。

特点:

#. 使用简单
#. 不需要服务器资源
#. 允许用户使用微博账号登录
#. 在站点上形成一个社区

现有的功能:

#. 用户可以通过新浪微博,腾讯微博或者ezComment的账号登录并评论你的站点的内容
#. 用户可以回复评论, 评论线索化显示


将来会加入的功能:

#. 结合站点本身的用户系统
#. 在你的站点形成一个社区
#. 用户档案
#. Email 订阅，有回复时通知订阅的用户
#. 抓取新浪微博等上面相关的内容显示在对应的文章下面
#. 垃圾评论过滤
#. 评论管理
#. 图片上传


如何使用
-------------------

在站点的页面加入下面的代码

:: 

    <div id="ezc_thread"></div> 
    <script type="text/javascript"> 
        /* * * CONFIGURATION VARIABLES: EDIT BEFORE PASTING INTO YOUR WEBPAGE * * */
        var ezc_shortname = 'test'; // required: replace example with your forum shortname

        // The following are highly recommended additional parameters. Remove the slashes in front to use.
        var ezc_identifier = 'unique-identity-id-1234';
        var ezc_url = document.location.href;

        /* * * DON'T EDIT BELOW THIS LINE * * */
        (function() {
            var ezc = document.createElement('script'); ezc.type = 'text/javascript'; ezc.async = true;
            ezc.src = 'http://comment.ezengege.com/forum/test/embed.js';
            (document.getElementsByTagName('head')[0] || document.getElementsByTagName('body')[0]).appendChild(ezc);
        })();
    </script> 
    <a href="http://comment.ezengage.com" class="ezc-brlink">comments powered by <span class="logo-ezcomment">ezComment</span></a> 


`ezc_shortname` 这个变量来表示你的站点。 `ezc_identifier` 这个变量用来标识当前的页面。
