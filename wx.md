### 调整方案
#### 前提
- 保证原系统不受影响
- 公众号A:已认证
- 原系统域名:www.old.com

#### 第一步
在原系统的网站的public目录下放置get-weixin-code.html,可以二级目录,可以改名字
要求最终要存在一个路径比如`http://www.old.com/XX/某路由` 或者`http://www.old.com/get-weixin-code.html`
在浏览器里边访问这路径的时候会提示说appid参数错误,大致如下
>
&nbsp;&nbsp;&nbsp;![Alt text](https://res.wx.qq.com/connect/zh_CN/htmledition/images/icon80_smile181c98.png "Optional title")   
AppID 参数错误

记下这个路由,这里我们记为 URL_A

#### 第二步
修改上线易系统自动生成的菜单链接
>https://open.weixin.qq.com/connect/oauth2/authorize?appid=wx768bb13db1cdb0c2&redirect_uri=http%3A%2F%2Fwww.shangxiane.net%2Fweixin%2F5724b8fde2d89c759f2c03eb%2Fproduct&response_type=code&scope=snsapi_base&state=%2Fweixin%2F5724b8fde2d89c759f2c03eb%2Fproduct#wechat_redirect`

修改为

>URL_A?appid=wx768bb13db1cdb0c2&redirect_uri=http%3A%2F%2Fwww.shangxiane.net%2Fweixin%2F5724b8fde2d89c759f2c03eb%2Fproduct&response_type=code&scope=snsapi_base&state=%2Fweixin%2F5724b8fde2d89c759f2c03eb%2Fproduct#wechat_redirect

#### 第三步
前两步做完之后应该已经能进去商城了,但是应该还不能支付
所以第三步就是在公众号A的微信公众号台设置支付相关的参数,具体设置可以参照上线易后台的引导,如果有些参数已经存在(那么应该是为了原系统设置的),不要动已经设置好的参数,再添加一个即可

__一个小细节__:
在设置过程中会遇到一个叫做js业务域名的东西,这个东西的作用是让你的网页里边的输入框被微信浏览器自动提醒说不要输入密码之类的(总之有点烦,这里没什么办法,自己选择吧,要么写原系统域名,要么写www.shangxaine.com)
