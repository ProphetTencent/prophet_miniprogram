prophet miniprogram
===========



项目介绍
-----

将腾讯云智能客服系统嵌入小程序，实现智能问答，并主要以组件形式进行智能客服系统定制化功能开发。

组件列表
-----

* 菜单消息 smartqa.wpy
* ……

用法
-----


项目使用wepy框架开发组件, 详见[wepy官方文档](https://tencent.github.io/wepy/document.html)。<br>
下载component嵌入到开发者自己的项目中，并在合适的页面位置引用组件即可使用。<br>


本项目中index.wpy 提供了 使用smartqa组件的一个简单示例:

```html
    <view class="smartquery">
      <smartqa sdkappid="" appid="" identifier="" botid="" :fromusername.sync="globalNickName"></smartqa>
    </view>
```

开发者需要填上在腾讯云智能客服系统中的相关信息(appid, sdkappid, identifier, botid)<br>
此外，还需要在smart.wpy中填上账号的 `usersig` 后即可将小程序绑定到机器人的智能问答上。


```javascript
      var random = parseInt(Math.random() * 1000000, 10) + 1
      var usersig = ''
      var queryurl = 'https://yun.tim.qq.com/v3/prophet/queryanswer?appid=' + this.appid + '&sdkappid=' + this.sdkappid +
        '&identifier=' + this.identifier + '&usersig=' + usersig + '&random=' + random +'&contenttype=json'
```

