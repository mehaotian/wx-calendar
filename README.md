> 恍恍惚惚开发小程序也有一段时间了，最近要做一个关于打卡的小程序，最终还是翻遍全网，依然找不到一款比较随眼缘的日历打卡的相关组件，所以，老样子，自己开发一个呗。（代码比较简单，只是提供一个思路，样式可以自己去样式表修改，如果有需要，文章留言，如果多的话，我会加上换肤，样式自定义等扩展功能，有需求，就留言吧，谢谢大家了，如果有错误，请您一定告诉我）

<hr>
#### 先来看看什么样子
![回到今天.gif](https://upload-images.jianshu.io/upload_images/4472817-b35ecedf5b67969a.gif?imageMogr2/auto-orient/strip)


#### 一.主要功能
1. 日期选择
“看第一预览图”
2. 日期切换
![日期选择.gif](https://upload-images.jianshu.io/upload_images/4472817-0aafeaa54126c087.gif?imageMogr2/auto-orient/strip)

3. 月份切换
![月份选择.gif](https://upload-images.jianshu.io/upload_images/4472817-2e80123fff9195d2.gif?imageMogr2/auto-orient/strip)
4. 回到今天
“看第一预览图”
5. 记录选中
![选中状态.png](https://upload-images.jianshu.io/upload_images/4472817-7f9bf75deb6c35fe.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#### 二.使用

最下面放上下载地址

1.  代码结构

将下载下来的文件 `wx-calendar.rar` 解压放到 `components` 文件夹下
![image.png](https://upload-images.jianshu.io/upload_images/4472817-5ee1cb17d5a558b1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

1.  引入代码

打开`pages/xxx/xxx.json`   xxx 为你需要引入的文件名 ，已xxx = index 为例
``` js
// pages/index/index.js
{
  "usingComponents": {
    "calendar": "/components/calendar/calendar"
  }
}

```
2. 使用代码
打开`pages/xxx/xxx.wxml`   xxx 为你需要引入的文件名 ，已xxx = index 为例

``` html
// pages/index/index.wxml
<!-- 
 * 日历选择组件
 * selected [Arrey] 那些日期被选中
 * bindselect [function] 日历是否被打开 
 * bindgetdate [function] 当前选择的日期
 * is-open [Boolean} 是否开启插入模式
  -->
<!-- <view class='other'>我是其他元素</view> -->
<calendar selected="{{selected}}" bindselect="bindselect" bindgetdate="bindgetdate" />

```
``` js
// pages/index/index.js
Page({

  /**
   * 页面的初始数据
   */
  data: {
    selected: [
      {
        date: '2018-5-21'
      }, {
        date: '2018-5-22'
      },{
        date: '2018-5-24'
      },{
        date: '2018-5-25'
      }
    ]
  },

  /**
   * 生命周期函数--监听页面加载
   */
  onLoad: function (options) { },
  /**
  * 日历是否被打开
  */
  bindselect(e) {
    console.log(e.detail.ischeck)
  },
  /**
   * 获取选择日期
   */
  bindgetdate(e) {
    let time = e.detail;
    console.log(time)

  }
})

```

#### 三.相关属性说明

|      参数名     |       默认值     |  说明  |
| :-:      | :-----:  | :----: |
|`selected `       | [Array]          |   记录值     |
|`bindselect `      |  [function]  |   日历是否被打开   |
| `bindgetdate `        |  [function]|   被选中的日期         |
|`is-open`      | [boolean]  false   |  是否为插入模式（可以被插入到‘dom’里） |


以上，就是组件的时候方法了，如果使用过程中，有问题可以联系我。

`wx-calendar组件` : [代码下载](https://github.com/mehaotian/wx-calendar/releases/tag/1.0)


