# Tabs

Tabs是一种常见的界面导航结构。通过页签容器，用户可以快捷地访问应用的不同模块。具体用法请参考[Tabs API](../reference/arkui-js/js-components-container-tabs.md)。


## 创建Tabs

在pages/index目录下的hml文件中创建一个Tabs组件。

```
<!-- index.hml -->
<div class="container" >
  <tabs> <tab-bar>
      <text>item1</text>
      <text>item2</text>
    </tab-bar>
    <tab-content>
      <div class="text">
        <text>content1</text>
      </div>
      <div class="text">
        <text>content2</text>
      </div>
    </tab-content>
  </tabs>
</div>
```

```
/* xxx.css */
.container {
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-color: #F1F3F5;
}
.text{
  width: 100%;
  height: 100%;
  justify-content: center;
  align-items: center;
}
```

![zh-cn_image_0000001165191390](figures/zh-cn_image_0000001165191390.gif)


## 设置Tabs方向

Tabs默认展示索引为index的标签及内容。通过设置vertical属性使组件纵向展示。

```
<!-- index.hml -->
<div class="container" style="background-color:#F1F3F5;">
  <tabs index="1"  vertical="true">
    <tab-bar >
      <text>item1</text>
      <text style="margin-top: 50px;">item2</text>
    </tab-bar>
    <tab-content>
      <div>
        <image src="common/images/bg-tv.jpg" style="object-fit: contain;"> </image>
      </div>
      <div>
        <image src="common/images/img1.jpg" style="object-fit: contain;"> </image>
      </div>
    </tab-content>
  </tabs>
</div>
```

![zh-cn_image_0000001208908643](figures/zh-cn_image_0000001208908643.gif)

设置mode属性使tab-bar的子组件均分，设置scrollable属性使tab-content不可进行左右滑动切换内容。

```
<!-- index.hml -->
<div class="container" style="background-color:#F1F3F5;">
  <tabs style="margin-top: 30px;">
    <tab-bar mode="fixed">
      <text>item1</text>
      <text>item2</text>
    </tab-bar>
    <tab-content scrollable="false">
      <div>
        <image src="common/images/bg-tv.jpg" style="object-fit: contain;"> </image>
      </div>
      <div>
        <image src="common/images/img2.jpg" style="object-fit: contain;"> </image>
      </div>
    </tab-content>
  </tabs>
</div>
```

![zh-cn_image_0000001209028575](figures/zh-cn_image_0000001209028575.gif)


## 设置样式

设置Tabs背景色及边框和tab-content布局。
```
<!-- index.hml -->
<div class="container">
  <tabs class="tabs">
    <tab-bar class="tabBar">
      <text class="tabBarItem">item1</text>
      <text class="tabBarItem">item2</text>
    </tab-bar>
    <tab-content class="tabContent">
      <div class="tabContent">
        <text>content1</text>
      </div>
      <div class="tabContent" >
        <text>content2</text>
      </div>
    </tab-content>
  </tabs>
</div>
```

```
/* xxx.css */
.container {
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
 background-color:#F1F3F5;
}
.tabs{
  margin-top: 20px;
 border: 1px solid #2262ef;
  width: 99%;
  padding: 10px;
}
.tabBar{
  width: 100%;
  border: 1px solid #78abec;
}
.tabContent{
  width: 100%;
  margin-top: 10px;
  height: 300px;
  color: blue;   
  justify-content: center;  align-items: center;
}
```

![zh-cn_image_0000001163388642](figures/zh-cn_image_0000001163388642.gif)


## 显示页签索引

开发者可以为Tabs添加change事件，实现页签切换后显示当前页签索引的功能。

```
<!-- index.hml -->
<div class="container" style="background-color:#F1F3F5;">
  <tabs class="tabs" onchange="tabChange">
    <tab-bar class="tabBar">
      <text class="tabBarItem">item1</text>
      <text class="tabBarItem">item2</text>
    </tab-bar>
    <tab-content class="tabContent">
      <div>
        <image src="common/images/bg-tv.jpg" style="object-fit: contain;"> </image>
      </div>
      <div>
        <image src="common/images/img1.jpg" style="object-fit: contain;"> </image>
      </div>
    </tab-content>
  </tabs>
</div>
```

```
/* index.js */
import prompt from '@system.prompt';
export default {
  tabChange(e){
    prompt.showToast({
      message: "Tab index: " + e.index
    })
  }
}
```

![zh-cn_image_0000001163228638](figures/zh-cn_image_0000001163228638.gif)


> ![icon-note.gif](public_sys-resources/icon-note.gif) **说明：**
>
> - tabs子组件仅支持一个[\<tab-bar>](../reference/arkui-js/js-components-container-tab-bar.md)和一个\[<tab-content>](../reference/arkui-js/js-components-container-tab-content.md)。


## 场景示例

在本场景中，开发者可以点击标签切换内容，选中后标签文字颜色变红，并显示下划线。

用tabs、tab-bar和tab-content实现点击切换功能，再定义数组，设置属性。使用change事件改变数组内的属性值实现变色及下划线的显示。

```
<!-- index.hml -->
<div class="container">
  <tabs onchange="changeTabactive">
    <tab-content>
      <div class="item-container" for="datas.list">
        <div if="{{$item.title=='List1'?true:false}}">
          <image src="common/images/bg-tv.jpg" style="object-fit: contain;"> </image>
        </div>
        <div if="{{$item.title=='List2'?true:false}}">
          <image src="common/images/img1.jpg" style="object-fit: none;"> </image>
        </div>
        <div if="{{$item.title=='List3'?true:false}}">
          <image src="common/images/img2.jpg" style="object-fit: contain;"> </image>
        </div>
      </div>
    </tab-content>
    <tab-bar class="tab_bar mytabs" mode="scrollable">
      <div class="tab_item" for="datas.list">
        <text style="color: {{$item.color}};">{{$item.title}}</text>
        <div class="underline-show" if="{{$item.show}}"></div>
        <div class="underline-hide" if="{{!$item.show}}"></div>
      </div>
    </tab-bar>
  </tabs>
</div>
```

```
/* xxx.css */
.container{
background-color:#F1F3F5;
}
.tab_bar {
  width: 100%;
}
.tab_item {
  flex-direction: column;
  align-items: center;
}
.tab_item text {
  font-size: 32px;
}
.item-container {
  justify-content: center;
  flex-direction: column;
}
.underline-show {
  height: 2px;
  width: 160px;
  background-color: #FF4500;
  margin-top: 7.5px;
}
.underline-hide {
  height: 2px;
  margin-top: 7.5px;
  width: 160px;
}
```

```
/* index.js */
import prompt from '@system.prompt';
export default {
  data() {
    return {
      datas: {
        color_normal: '#878787',
        color_active: '#ff4500',
        show: true,
        list: [{
          i: 0,
          color: '#ff4500',
          show: true,
          title: 'List1'
        }, {
          i: 1,
          color: '#878787',
          show: false,
          title: 'List2'
        }, {
           i: 2,
           color: '#878787',
           show: false,
           title: 'List3'
        }]
      }
    }
  },
  changeTabactive (e) {
    for (let i = 0; i < this.datas.list.length; i++) {
      let element = this.datas.list[i];
      element.show = false;
      element.color = this.datas.color_normal;
      if (i === e.index) {
        element.show = true;
        element.color = this.datas.color_active;
      }
    }
  }
}
```

![zh-cn_image_0000001163228602](figures/zh-cn_image_0000001163228602.gif)
