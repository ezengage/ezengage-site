RESTful API
=================
ezEngage 提供RESTful API 来读取用户认证信息和推送消息到社交网络。

使用RESTful API 需要你能够发送HTTP GET/POST 请求，并能解析JSON格式的响应数据。

在发送请求时需要用到的你的ezEngage APP Key。(参考: :ref:`find-ezengage-app-info`)


.. _api-get-profile:

Get Profile
---------------
通过token获取用户档案

:: 

  GET  http://api.ezengage.com/api/v1/profile.json?app_key={app_key}&token={token}

其中参数 token 为 `token_url` 接受到的token, app_key 为你的应用的app key 。

返回代码:

* 200 OK 表示成功
* 其他代码都表示错误

返回结果格式示例::

    {
        "display_name": "ezEngage", 
        "gender": "male", 
        "preferred_username": "ezEngage", 
        "avatar_url": "http://tp2.sinaimg.cn/1934046393/50/1298645552/1", 
        "provider_code": "sinaweibo", 
        "provider_name": "新浪微博", 
        "identity": "http://t.sina.com.cn/1934046393"
    }

Profile 字段说明
^^^^^^^^^^^^^^^^^^

下面的表格列出了返回的用户档案中各个字段的含义。

=====================      =================================================== =======================
字段                        描述                                               可用性
=====================      =================================================== =======================
identity                   用户的Identity                                      总是可用  
provider_code              供应商代码                                          总是可用
provider_name              供应商的的名称,可以显示给用户                       总是可用
preferred_username         建议使用的用户名                                    总是可用
display_name               用于显示的名称,可以作昵称之类的用途                 总是可用
name                       姓名                                                人人网
gender                     性别                                                大部分可用
avatar_url                 头像链接                                            大部分可用
=====================      =================================================== =======================


.. _api-update-status:

Update Status
---------------
推送消息到微博或社交网络

::  

   POST http://api.ezengage.com/api/v1/status.json 

请求参数:

==========  ========= ===================
字段        是否必需  意义
==========  ========= ===================
identity    是        用户的identity
status      是        要发送的消息
app_key     是        你的应用的app key
long        否        用户的位置信息(经度)
lat         否        用户的位置信息(纬度)
==========  ========= ===================

.. note::
   status 字段的长度如果超过了供应商的限制（比如新浪微博的140字), ezEngage 会在发送前进行截断。
   经度和纬度只有部分供应商支持，不支持的供应商这两个参数将被忽略。


返回状态码:

* 201 Created  发送成功
* 其他代码都表示错误

