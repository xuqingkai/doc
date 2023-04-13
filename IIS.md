### 反向代理
- 下载ARR：https://www.iis.net/downloads/microsoft/application-request-routing
- 安装后，打开IIS，指向服务器，找到“Application Request...”图标，点击打开，点击打开右侧菜单Server Proxy Setting..，勾选enable proxy
- 下载UrlRewrite：https://www.iis.net/downloads/microsoft/url-rewrite
- 安装后，指向要反向代理的网站，找到“URL重写”图标，添加空白规则
- 1，随便起个规则名，模式输入：(.*)
- 2，操作/操作属性/重写URL，输入要被代理的网站地址：http://www.source.com/cn/{R:1}
- 3，如果需要根据域名重写，则添加条件，条件输入定义一个变量名：{HTTP_HOST}，模式：^www\.(.+).(com|cn)$
- 4，操作/操作属性/重写URL，输入要被代理的网站地址：http://www.source.com/{HTTP_HOST}/{R:1}
