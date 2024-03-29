# Path<a name="ZH-CN_TOPIC_0000001192755118"></a>

>![](../../public_sys-resources/icon-note.gif) **说明：** 
>该组件从API Version 7开始支持。后续版本如有新增内容，则采用上角标单独标记该内容的起始版本。

路径绘制组件。

## 权限列表<a name="section53281531154915"></a>

无

## 子组件<a name="section53306512504"></a>

无

## 属性<a name="section3525926155013"></a>

<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.1.6.1.1"><p>参数名称</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.1.6.1.2"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.1.6.1.3"><p>默认值</p>
</th>
<th class="cellrowborder" valign="top" width="15.559999999999999%" id="mcps1.1.6.1.4"><p>必填</p>
</th>
<th class="cellrowborder" valign="top" width="24.44%" id="mcps1.1.6.1.5"><p>参数描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.1.6.1.1 "><p>width</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.1.6.1.2 "><p>Length</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.1.6.1.3 "><p>0</p>
</td>
<td class="cellrowborder" valign="top" width="15.559999999999999%" headers="mcps1.1.6.1.4 "><p>否</p>
</td>
<td class="cellrowborder" valign="top" width="24.44%" headers="mcps1.1.6.1.5 "><p>路径所在矩形的宽度。</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.1.6.1.1 "><p>height</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.1.6.1.2 "><p>Length</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.1.6.1.3 "><p>0</p>
</td>
<td class="cellrowborder" valign="top" width="15.559999999999999%" headers="mcps1.1.6.1.4 "><p>否</p>
</td>
<td class="cellrowborder" valign="top" width="24.44%" headers="mcps1.1.6.1.5 "><p>路径所在矩形的高度。</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.1.6.1.1 "><p>commands</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.1.6.1.2 "><p>string</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.1.6.1.3 "><p>''</p>
</td>
<td class="cellrowborder" valign="top" width="15.559999999999999%" headers="mcps1.1.6.1.4 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="24.44%" headers="mcps1.1.6.1.5 "><p>路径绘制的命令字符串。</p>
</td>
</tr>
</tbody>
</table>

支持的绘制命令如下：

-   M = moveto
-   L = lineto
-   H = horizontal lineto
-   V = vertical lineto
-   C = curveto
-   S = smooth curveto
-   Q = quadratic Belzier curve
-   T = smooth quadratic Belzier curveto
-   A = elliptical Arc
-   Z = closepath

如 commands\('M0 20 L50 50 L50 100 Z'\)定义了一条路径，开始于位置（0，20），到达位置（50，50）后再到（50，100），最后在（0，20）处关闭路径。

## 示例<a name="section4459736105512"></a>

```
@Entry
@Component
struct PathExample {
  build() {
    Column({ space: 5 }) {
      Text('Straight line').fontSize(9).fontColor(0xCCCCCC).width('90%')
      Path().width(300).height(10).commands('M0 0 L900 0').stroke(Color.Black).strokeWidth(3)

      Text('Straight line graph').fontSize(9).fontColor(0xCCCCCC).width('90%')
      Flex({ justifyContent: FlexAlign.SpaceAround }) {
        // 先后执行MoveTo(150, 0), LineTo(300, 300), LineTo(0, 300), ClosePath()
        Path().width(100).height(100).commands('M150 0 L300 300 L0 300 Z')
        // 先后执行MoveTo(0, 0), HorizontalLineto(300), VerticalLineto(300), HorizontalLineto(0), ClosePath()
        Path().width(100).height(100).commands('M0 0 H300 V300 H0 Z')
        // 先后执行MoveTo(150, 0), LineTo(0, 150), LineTo(60, 300), LineTo(240, 300), LineTo(300, 150), ClosePath()
        Path().width(100).height(100).commands('M150 0 L0 150 L60 300 L240 300 L300 150 Z')
      }.width('100%')

      Text('Curve graphics').fontSize(9).fontColor(0xCCCCCC).width('90%')
      Flex({ justifyContent: FlexAlign.SpaceAround }) {
        // 先后执行MoveTo(0, 300),(150, 0)(300, 300)两点之间画曲线, ClosePath()
        Path().width(100).height(100).commands("M0 300 S150 0 300 300 Z")
        // 先后执行MoveTo(0, 150),(0, 150)(150, 0)(300, 150)三点之间依次画曲线, LineTo(150, 300),ClosePath()
        Path().width(100).height(100).commands('M0 150 C0 150 150 0 300 150 L150 300 Z')
      }
    }.width('100%').margin({ top: 5 })
  }
}
```

![](figures/path.png)

