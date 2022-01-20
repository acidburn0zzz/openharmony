# 图像效果<a name="ZH-CN_TOPIC_0000001237715097"></a>

>![](../../public_sys-resources/icon-note.gif) **说明：** 
>从API Version 7开始支持。后续版本如有新增内容，则采用上角标单独标记该内容的起始版本。

## 权限列表<a name="section781125411508"></a>

无

## 属性<a name="section6820191711316"></a>

<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="15.409999999999998%" id="mcps1.1.5.1.1"><p>名称</p>
</th>
<th class="cellrowborder" valign="top" width="20.91%" id="mcps1.1.5.1.2"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="23.119999999999997%" id="mcps1.1.5.1.3"><p>默认值</p>
</th>
<th class="cellrowborder" valign="top" width="40.56%" id="mcps1.1.5.1.4"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="15.409999999999998%" headers="mcps1.1.5.1.1 "><p>blur</p>
</td>
<td class="cellrowborder" valign="top" width="20.91%" headers="mcps1.1.5.1.2 "><p>number</p>
</td>
<td class="cellrowborder" valign="top" width="23.119999999999997%" headers="mcps1.1.5.1.3 "><p>-</p>
</td>
<td class="cellrowborder" valign="top" width="40.56%" headers="mcps1.1.5.1.4 "><p>为当前组件添加内容模糊效果，入参为模糊半径，模糊半径越大越模糊，为0时不模糊。</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="15.409999999999998%" headers="mcps1.1.5.1.1 "><p>backdropBlur</p>
</td>
<td class="cellrowborder" valign="top" width="20.91%" headers="mcps1.1.5.1.2 "><p>number</p>
</td>
<td class="cellrowborder" valign="top" width="23.119999999999997%" headers="mcps1.1.5.1.3 "><p>-</p>
</td>
<td class="cellrowborder" valign="top" width="40.56%" headers="mcps1.1.5.1.4 "><p>为当前组件添加背景模糊效果，入参为模糊半径，模糊半径越大越模糊，为0时不模糊。</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="15.409999999999998%" headers="mcps1.1.5.1.1 "><p>shadow</p>
</td>
<td class="cellrowborder" valign="top" width="20.91%" headers="mcps1.1.5.1.2 "><p>{</p>
<p>radius: number,</p>
<p>color?: Color,</p>
<p>offsetX?: number,</p>
<p>offsetY?: number</p>
<p>}</p>
</td>
<td class="cellrowborder" valign="top" width="23.119999999999997%" headers="mcps1.1.5.1.3 "><p>-</p>
</td>
<td class="cellrowborder" valign="top" width="40.56%" headers="mcps1.1.5.1.4 "><p>为当前组件添加阴影效果，入参为模糊半径(必填)、阴影的颜色(可选，默认为灰色)、X轴的偏移量(可选，默认为0)，Y轴的偏移量(可选，默认为0)，偏移量单位为px。</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="15.409999999999998%" headers="mcps1.1.5.1.1 "><p>grayscale</p>
</td>
<td class="cellrowborder" valign="top" width="20.91%" headers="mcps1.1.5.1.2 "><p>number</p>
</td>
<td class="cellrowborder" valign="top" width="23.119999999999997%" headers="mcps1.1.5.1.3 "><p>0.0</p>
</td>
<td class="cellrowborder" valign="top" width="40.56%" headers="mcps1.1.5.1.4 "><p>为当前组件添加灰度效果。值定义为灰度转换的比例，入参1.0则完全转为灰度图像，入参则0.0图像无变化，入参在0.0和1.0之间时，效果呈线性变化。（百分比)</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="15.409999999999998%" headers="mcps1.1.5.1.1 "><p>brightness</p>
</td>
<td class="cellrowborder" valign="top" width="20.91%" headers="mcps1.1.5.1.2 "><p>number</p>
</td>
<td class="cellrowborder" valign="top" width="23.119999999999997%" headers="mcps1.1.5.1.3 "><p>1.0</p>
</td>
<td class="cellrowborder" valign="top" width="40.56%" headers="mcps1.1.5.1.4 "><p>为当前组件添加高光效果，入参为高光比例，值为1时没有效果，小于1时亮度变暗，0为全黑；大于1时亮度增加，数值越大亮度越大。</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="15.409999999999998%" headers="mcps1.1.5.1.1 "><p>saturate</p>
</td>
<td class="cellrowborder" valign="top" width="20.91%" headers="mcps1.1.5.1.2 "><p>number</p>
</td>
<td class="cellrowborder" valign="top" width="23.119999999999997%" headers="mcps1.1.5.1.3 "><p>1.0</p>
</td>
<td class="cellrowborder" valign="top" width="40.56%" headers="mcps1.1.5.1.4 "><p>为当前组件添加饱和度效果，饱和度为颜色中的含色成分和消色成分(灰)的比例，入参为1时，显示原图像，大于1时含色成分越大，饱和度越大；小于1时消色成分越大，饱和度越小。（百分比）</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="15.409999999999998%" headers="mcps1.1.5.1.1 "><p>contrast</p>
</td>
<td class="cellrowborder" valign="top" width="20.91%" headers="mcps1.1.5.1.2 "><p>number</p>
</td>
<td class="cellrowborder" valign="top" width="23.119999999999997%" headers="mcps1.1.5.1.3 "><p>1.0</p>
</td>
<td class="cellrowborder" valign="top" width="40.56%" headers="mcps1.1.5.1.4 "><p>为当前组件添加对比度效果，入参为对比度的值，值为1时，显示原图；大于1时，值越大对比度越高，图像越清晰醒目；小于1时，值越小对比度越低；当对比度为0时，图像变为全灰。（百分比）</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="15.409999999999998%" headers="mcps1.1.5.1.1 "><p>invert</p>
</td>
<td class="cellrowborder" valign="top" width="20.91%" headers="mcps1.1.5.1.2 "><p>number</p>
</td>
<td class="cellrowborder" valign="top" width="23.119999999999997%" headers="mcps1.1.5.1.3 "><p>0</p>
</td>
<td class="cellrowborder" valign="top" width="40.56%" headers="mcps1.1.5.1.4 "><p>反转输入的图像。入参为图像反转的比例。值为1时完全反转。值为0则图像无变化。（百分比）</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="15.409999999999998%" headers="mcps1.1.5.1.1 "><p>colorBlend <sup><span>8+</span></sup></p>
</td>
<td class="cellrowborder" valign="top" width="20.91%" headers="mcps1.1.5.1.2 "><p>Color</p>
</td>
<td class="cellrowborder" valign="top" width="23.119999999999997%" headers="mcps1.1.5.1.3 "><p>-</p>
</td>
<td class="cellrowborder" valign="top" width="40.56%" headers="mcps1.1.5.1.4 "><p>为当前组件添加颜色叠加效果，入参为叠加的颜色。</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="15.409999999999998%" headers="mcps1.1.5.1.1 "><p>sepia</p>
</td>
<td class="cellrowborder" valign="top" width="20.91%" headers="mcps1.1.5.1.2 "><p>number</p>
</td>
<td class="cellrowborder" valign="top" width="23.119999999999997%" headers="mcps1.1.5.1.3 "><p>0</p>
</td>
<td class="cellrowborder" valign="top" width="40.56%" headers="mcps1.1.5.1.4 "><p>将图像转换为深褐色。入参为图像反转的比例。值为1则完全是深褐色的，值为0图像无变化。 （百分比）</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="15.409999999999998%" headers="mcps1.1.5.1.1 "><p>hueRotate</p>
</td>
<td class="cellrowborder" valign="top" width="20.91%" headers="mcps1.1.5.1.2 "><p>Angle</p>
</td>
<td class="cellrowborder" valign="top" width="23.119999999999997%" headers="mcps1.1.5.1.3 "><p>0deg</p>
</td>
<td class="cellrowborder" valign="top" width="40.56%" headers="mcps1.1.5.1.4 "><p>为当前组件添加色相旋转效果，入参为旋转的角度值。当入参为0deg时图像无变化(默认值是0deg)，入参没有最大值，超过360deg的值相当于又绕一圈。</p>
</td>
</tr>
</tbody>
</table>

## 示例<a name="section4278134412416"></a>

```
@Entry
@Component
struct ImageEffectsExample {
  build() {
    Column({space: 10}) {
      // 对字体进行模糊
      Text('font blur').fontSize(15).fontColor(0xCCCCCC).width('90%')
      Text('text').blur(3).width('90%').height(40)
        .fontSize(16).backgroundColor(0xF9CF93).padding({ left: 5 })

      // 对背景进行模糊
      Text('backdropBlur').fontSize(15).fontColor(0xCCCCCC).width('90%')
      Text().width('90%').height(40).fontSize(16).backdropBlur(3)
        .backgroundImage('/comment/bg.jpg')
        .backgroundImageSize({ width: 1200, height: 160 })

      Text('shadow').fontSize(15).fontColor(0xCCCCCC).width('90%')
      Image($r('app.media.bg')).width('90%').height(40)
        .shadow({ radius: 10, color: Color.Gray, offsetX: 5, offsetY: 5 })

      Text('grayscale').fontSize(15).fontColor(0xCCCCCC).width('90%')
      Image($r('app.media.bg')).width('90%').height(40).grayscale(0.6)

      Text('brightness').fontSize(15).fontColor(0xCCCCCC).width('90%')
      Image($r('app.media.bg')).width('90%').height(40).brightness(2.0)

      Text('saturate').fontSize(15).fontColor(0xCCCCCC).width('90%')
      Image($r('app.media.bg')).width('90%').height(40).saturate(2.0)

      Text('contrast').fontSize(15).fontColor(0xCCCCCC).width('90%')
      Image($r('app.media.bg')).width('90%').height(40).contrast(2.0)

      Text('invert').fontSize(15).fontColor(0xCCCCCC).width('90%')
      Image($r('app.media.bg')).width('90%').height(40).invert(1)

      Text('hueRotate').fontSize(15).fontColor(0xCCCCCC).width('90%')
      Image($r('app.media.bg')).width('90%').height(40).hueRotate(90)
    }.width('100%').margin({ top: 5 })
  }
}
```

![](figures/2222.png)
