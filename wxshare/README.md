## 微信小程序 将此页面 分享到朋友圈 or 发送给朋友
---
1. defaultpyq 使用 API 默认
2. cusomizepyq 使用 框架 自定义
3. buttondefault 使用 button 发送给朋友

---
### 方法一 使用 API 默认
wx.showShareMenu  
[https://developers.weixin.qq.com/miniprogram/dev/api/share/wx.showShareMenu.html](https://developers.weixin.qq.com/miniprogram/dev/api/share/wx.showShareMenu.html)  
示例代码    
```
/**
* 在 onLoad/onShow 事件调用 wx.showShareMenu
*/
wx.showShareMenu({
  withShareTicket: true,
  menus: ['shareAppMessage', 'shareTimeline']
})
```
---

### 方法二 使用 框架 自定义
概述  
[https://developers.weixin.qq.com/miniprogram/dev/framework/open-ability/share-timeline.html](https://developers.weixin.qq.com/miniprogram/dev/framework/open-ability/share-timeline.html)  

onShareAppMessage  
[https://developers.weixin.qq.com/miniprogram/dev/reference/api/Page.html#onShareAppMessage-Object-object](https://developers.weixin.qq.com/miniprogram/dev/reference/api/Page.html#onShareAppMessage-Object-object)

onShareTimeline()  
[https://developers.weixin.qq.com/miniprogram/dev/reference/api/Page.html#onShareTimeline](https://developers.weixin.qq.com/miniprogram/dev/reference/api/Page.html#onShareTimeline)

示例代码 
```
onShareAppMessage: function (res) {
    if (res.from === 'button') {
      // 来自页面内转发按钮
      console.log(res.target)
    }
    return {
      // title: '自定义转发标题',
      // path: '/page/user?id=123'
    }
  },
onShareTimeline: function (res) {
    if (res.from === 'button') {
      // 来自页面内转发按钮
      console.log(res.target)
    }
    return {
      title: '自定义转发标题',
      // path: '/page/user?id=123'
    }
  }
```

---
### 使用 button 发送给朋友  
[https://developers.weixin.qq.com/miniprogram/dev/reference/api/Page.html#onShareAppMessage-Object-object](https://developers.weixin.qq.com/miniprogram/dev/reference/api/Page.html#onShareAppMessage-Object-object)   
示例代码 
```
/**
* 设置 button 组件 open-type="share"
*/
<button open-type="share">shareButtonFriend</button>
```
