1，如果提示当前地区不提供服务：OpenAI’s services are not available in your country，则右键任何一个网页的源代码，找到任何一个可见元素，加一个click事件，如下
```
<p onclick="javascript:window.localStorage.removeItem(Object.keys(window.localStorage).find(i=>i.startsWith('@@auth0spajs')));alert('ok');"></p>
```
点击执行下
