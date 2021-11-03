# dialog<a name="ZH-CN_TOPIC_0000001209210697"></a>

-   [权限列表](#zh-cn_topic_0000001173324657_section11257113618419)
-   [子组件](#zh-cn_topic_0000001173324657_section9288143101012)
-   [属性](#zh-cn_topic_0000001173324657_section2907183951110)
-   [样式](#zh-cn_topic_0000001173324657_section5775351116)
-   [事件](#zh-cn_topic_0000001173324657_section8562129182916)
-   [方法](#zh-cn_topic_0000001173324657_section11753103216253)
-   [示例](#zh-cn_topic_0000001173324657_section6663311114620)

自定义弹窗容器。

## 权限列表<a name="zh-cn_topic_0000001173324657_section11257113618419"></a>

无

## 子组件<a name="zh-cn_topic_0000001173324657_section9288143101012"></a>

支持单个子组件。

## 属性<a name="zh-cn_topic_0000001173324657_section2907183951110"></a>

除支持[通用属性](js-components-common-attributes.md#ZH-CN_TOPIC_0000001163812208)外，支持如下属性：

<a name="zh-cn_topic_0000001173324657_tb330011ff53049a69f27cec012adf8c1"></a>
<table><thead align="left"><tr id="zh-cn_topic_0000001173324657_r4301f3a3b24c499c9bfc42b76ab785f9"><th class="cellrowborder" valign="top" width="19.598040195980403%" id="mcps1.1.6.1.1"><p id="zh-cn_topic_0000001173324657_a9ba8c579217b4b8b841b035f1d28b20e"><a name="zh-cn_topic_0000001173324657_a9ba8c579217b4b8b841b035f1d28b20e"></a><a name="zh-cn_topic_0000001173324657_a9ba8c579217b4b8b841b035f1d28b20e"></a>名称</p>
</th>
<th class="cellrowborder" valign="top" width="11.178882111788822%" id="mcps1.1.6.1.2"><p id="zh-cn_topic_0000001173324657_a633002333b024497914a4b172446f14e"><a name="zh-cn_topic_0000001173324657_a633002333b024497914a4b172446f14e"></a><a name="zh-cn_topic_0000001173324657_a633002333b024497914a4b172446f14e"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="9.899010098990102%" id="mcps1.1.6.1.3"><p id="zh-cn_topic_0000001173324657_a4950f7884c6540b9ad523ac34657d952"><a name="zh-cn_topic_0000001173324657_a4950f7884c6540b9ad523ac34657d952"></a><a name="zh-cn_topic_0000001173324657_a4950f7884c6540b9ad523ac34657d952"></a>默认值</p>
</th>
<th class="cellrowborder" valign="top" width="7.56924307569243%" id="mcps1.1.6.1.4"><p id="zh-cn_topic_0000001173324657_p58189597166"><a name="zh-cn_topic_0000001173324657_p58189597166"></a><a name="zh-cn_topic_0000001173324657_p58189597166"></a>必填</p>
</th>
<th class="cellrowborder" valign="top" width="51.754824517548236%" id="mcps1.1.6.1.5"><p id="zh-cn_topic_0000001173324657_a1313564aa9404a338447087d5918c17d"><a name="zh-cn_topic_0000001173324657_a1313564aa9404a338447087d5918c17d"></a><a name="zh-cn_topic_0000001173324657_a1313564aa9404a338447087d5918c17d"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0000001173324657_r06a481428e8d455fba919d3d4618be31"><td class="cellrowborder" valign="top" width="19.598040195980403%" headers="mcps1.1.6.1.1 "><p id="zh-cn_topic_0000001173324657_adb8a73146d764f2aab50fc046169ab26"><a name="zh-cn_topic_0000001173324657_adb8a73146d764f2aab50fc046169ab26"></a><a name="zh-cn_topic_0000001173324657_adb8a73146d764f2aab50fc046169ab26"></a>dragable<sup id="zh-cn_topic_0000001173324657_sup999420218191"><a name="zh-cn_topic_0000001173324657_sup999420218191"></a><a name="zh-cn_topic_0000001173324657_sup999420218191"></a><span>7+</span></sup></p>
</td>
<td class="cellrowborder" valign="top" width="11.178882111788822%" headers="mcps1.1.6.1.2 "><p id="zh-cn_topic_0000001173324657_a06898db2627246f78e85d4fbadeee85c"><a name="zh-cn_topic_0000001173324657_a06898db2627246f78e85d4fbadeee85c"></a><a name="zh-cn_topic_0000001173324657_a06898db2627246f78e85d4fbadeee85c"></a>boolean</p>
</td>
<td class="cellrowborder" valign="top" width="9.899010098990102%" headers="mcps1.1.6.1.3 "><p id="zh-cn_topic_0000001173324657_ae685ead324a647bcba1bbb45c9402dd6"><a name="zh-cn_topic_0000001173324657_ae685ead324a647bcba1bbb45c9402dd6"></a><a name="zh-cn_topic_0000001173324657_ae685ead324a647bcba1bbb45c9402dd6"></a>false</p>
</td>
<td class="cellrowborder" valign="top" width="7.56924307569243%" headers="mcps1.1.6.1.4 "><p id="zh-cn_topic_0000001173324657_p78183594166"><a name="zh-cn_topic_0000001173324657_p78183594166"></a><a name="zh-cn_topic_0000001173324657_p78183594166"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="51.754824517548236%" headers="mcps1.1.6.1.5 "><p id="zh-cn_topic_0000001173324657_a692121725a9b4ebbae65cd22b94b672e"><a name="zh-cn_topic_0000001173324657_a692121725a9b4ebbae65cd22b94b672e"></a><a name="zh-cn_topic_0000001173324657_a692121725a9b4ebbae65cd22b94b672e"></a>设置对话框是否支持拖拽。</p>
</td>
</tr>
</tbody>
</table>

>![](../../public_sys-resources/icon-note.gif) **说明：** 
>-   弹窗类组件不支持focusable、click-effect属性。

## 样式<a name="zh-cn_topic_0000001173324657_section5775351116"></a>

仅支持[通用样式](js-components-common-styles.md#ZH-CN_TOPIC_0000001163932190)中的width、height、margin、margin-\[left|top|right|bottom\]、margin-\[start|end\]样式。

## 事件<a name="zh-cn_topic_0000001173324657_section8562129182916"></a>

不支持[通用事件](js-components-common-events.md#ZH-CN_TOPIC_0000001209412119)，仅支持如下事件：

<a name="zh-cn_topic_0000001173324657_table20562102982910"></a>
<table><thead align="left"><tr id="zh-cn_topic_0000001173324657_row9562162932910"><th class="cellrowborder" valign="top" width="18.459999999999997%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0000001173324657_p195626291296"><a name="zh-cn_topic_0000001173324657_p195626291296"></a><a name="zh-cn_topic_0000001173324657_p195626291296"></a>名称</p>
</th>
<th class="cellrowborder" valign="top" width="30.769999999999996%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0000001173324657_p185622029202914"><a name="zh-cn_topic_0000001173324657_p185622029202914"></a><a name="zh-cn_topic_0000001173324657_p185622029202914"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="50.77%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0000001173324657_p9562132915297"><a name="zh-cn_topic_0000001173324657_p9562132915297"></a><a name="zh-cn_topic_0000001173324657_p9562132915297"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0000001173324657_row7562729142911"><td class="cellrowborder" valign="top" width="18.459999999999997%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0000001173324657_p145622291299"><a name="zh-cn_topic_0000001173324657_p145622291299"></a><a name="zh-cn_topic_0000001173324657_p145622291299"></a>cancel</p>
</td>
<td class="cellrowborder" valign="top" width="30.769999999999996%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0000001173324657_p356210295295"><a name="zh-cn_topic_0000001173324657_p356210295295"></a><a name="zh-cn_topic_0000001173324657_p356210295295"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="50.77%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0000001173324657_p55621629122916"><a name="zh-cn_topic_0000001173324657_p55621629122916"></a><a name="zh-cn_topic_0000001173324657_p55621629122916"></a>用户点击非dialog区域触发取消弹窗时触发的事件。</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001173324657_row154462392615"><td class="cellrowborder" valign="top" width="18.459999999999997%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0000001173324657_p84461834266"><a name="zh-cn_topic_0000001173324657_p84461834266"></a><a name="zh-cn_topic_0000001173324657_p84461834266"></a>show<sup id="zh-cn_topic_0000001173324657_sup2397204717198"><a name="zh-cn_topic_0000001173324657_sup2397204717198"></a><a name="zh-cn_topic_0000001173324657_sup2397204717198"></a><span>7+</span></sup></p>
</td>
<td class="cellrowborder" valign="top" width="30.769999999999996%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0000001173324657_p164468315263"><a name="zh-cn_topic_0000001173324657_p164468315263"></a><a name="zh-cn_topic_0000001173324657_p164468315263"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="50.77%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0000001173324657_p204465311269"><a name="zh-cn_topic_0000001173324657_p204465311269"></a><a name="zh-cn_topic_0000001173324657_p204465311269"></a>对话框弹出时触发该事件。</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001173324657_row28470175299"><td class="cellrowborder" valign="top" width="18.459999999999997%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0000001173324657_p2848161792917"><a name="zh-cn_topic_0000001173324657_p2848161792917"></a><a name="zh-cn_topic_0000001173324657_p2848161792917"></a>close<sup id="zh-cn_topic_0000001173324657_sup4231174871918"><a name="zh-cn_topic_0000001173324657_sup4231174871918"></a><a name="zh-cn_topic_0000001173324657_sup4231174871918"></a><span>7+</span></sup></p>
</td>
<td class="cellrowborder" valign="top" width="30.769999999999996%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0000001173324657_p128481917132913"><a name="zh-cn_topic_0000001173324657_p128481917132913"></a><a name="zh-cn_topic_0000001173324657_p128481917132913"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="50.77%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0000001173324657_p5848121742920"><a name="zh-cn_topic_0000001173324657_p5848121742920"></a><a name="zh-cn_topic_0000001173324657_p5848121742920"></a>对话框关闭时触发该事件。</p>
</td>
</tr>
</tbody>
</table>

## 方法<a name="zh-cn_topic_0000001173324657_section11753103216253"></a>

不支持[通用方法](js-components-common-methods.md#ZH-CN_TOPIC_0000001209252157)，仅支持如下方法。

<a name="zh-cn_topic_0000001173324657_table20753173210251"></a>
<table><thead align="left"><tr id="zh-cn_topic_0000001173324657_row575363214257"><th class="cellrowborder" valign="top" width="18.459999999999997%" id="mcps1.1.4.1.1"><p id="zh-cn_topic_0000001173324657_p157531032112517"><a name="zh-cn_topic_0000001173324657_p157531032112517"></a><a name="zh-cn_topic_0000001173324657_p157531032112517"></a>名称</p>
</th>
<th class="cellrowborder" valign="top" width="30.769999999999996%" id="mcps1.1.4.1.2"><p id="zh-cn_topic_0000001173324657_p77531632132518"><a name="zh-cn_topic_0000001173324657_p77531632132518"></a><a name="zh-cn_topic_0000001173324657_p77531632132518"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="50.77%" id="mcps1.1.4.1.3"><p id="zh-cn_topic_0000001173324657_p147531232132512"><a name="zh-cn_topic_0000001173324657_p147531232132512"></a><a name="zh-cn_topic_0000001173324657_p147531232132512"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0000001173324657_row15753113210251"><td class="cellrowborder" valign="top" width="18.459999999999997%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0000001173324657_p2314135812511"><a name="zh-cn_topic_0000001173324657_p2314135812511"></a><a name="zh-cn_topic_0000001173324657_p2314135812511"></a>show</p>
</td>
<td class="cellrowborder" valign="top" width="30.769999999999996%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0000001173324657_p7314115819256"><a name="zh-cn_topic_0000001173324657_p7314115819256"></a><a name="zh-cn_topic_0000001173324657_p7314115819256"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="50.77%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0000001173324657_p0314958162512"><a name="zh-cn_topic_0000001173324657_p0314958162512"></a><a name="zh-cn_topic_0000001173324657_p0314958162512"></a>弹出对话框。</p>
</td>
</tr>
<tr id="zh-cn_topic_0000001173324657_row393410526251"><td class="cellrowborder" valign="top" width="18.459999999999997%" headers="mcps1.1.4.1.1 "><p id="zh-cn_topic_0000001173324657_p7314358182512"><a name="zh-cn_topic_0000001173324657_p7314358182512"></a><a name="zh-cn_topic_0000001173324657_p7314358182512"></a>close</p>
</td>
<td class="cellrowborder" valign="top" width="30.769999999999996%" headers="mcps1.1.4.1.2 "><p id="zh-cn_topic_0000001173324657_p1231455814253"><a name="zh-cn_topic_0000001173324657_p1231455814253"></a><a name="zh-cn_topic_0000001173324657_p1231455814253"></a>-</p>
</td>
<td class="cellrowborder" valign="top" width="50.77%" headers="mcps1.1.4.1.3 "><p id="zh-cn_topic_0000001173324657_p10314105842512"><a name="zh-cn_topic_0000001173324657_p10314105842512"></a><a name="zh-cn_topic_0000001173324657_p10314105842512"></a>关闭对话框。</p>
</td>
</tr>
</tbody>
</table>

>![](../../public_sys-resources/icon-note.gif) **说明：** 
>dialog属性、样式均不支持动态更新。

## 示例<a name="zh-cn_topic_0000001173324657_section6663311114620"></a>

```
<!-- xxx.hml -->
<div class="doc-page">
  <div class="btn-div">
    <button type="capsule" value="Click here" class="btn" onclick="showDialog"></button>
  </div>
  <dialog id="simpledialog" class="dialog-main" oncancel="cancelDialog">
    <div class="dialog-div">
      <div class="inner-txt">
        <text class="txt">Simple dialog</text>
      </div>
      <div class="inner-btn">
        <button type="capsule" value="Cancel" onclick="cancelSchedule" class="btn-txt"></button>
        <button type="capsule" value="Confirm" onclick="setSchedule" class="btn-txt"></button>
      </div>
    </div>
  </dialog>
</div>
```

```
/* xxx.css */
.doc-page {
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.btn-div {
  width: 100%;
  height: 200px;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.btn {
  background-color: #F2F2F2;
  text-color: #0D81F2;
}
.txt {
  color: #000000;
  font-weight: bold;
  font-size: 39px;
}
.dialog-main {
  width: 500px;
}
.dialog-div {
  flex-direction: column;
  align-items: center;
}
.inner-txt {
  width: 400px;
  height: 160px;
  flex-direction: column;
  align-items: center;
  justify-content: space-around;
}
.inner-btn {
  width: 400px;
  height: 120px;
  justify-content: space-around;
  align-items: center;
}
.btn-txt {
  background-color: #F2F2F2;
  text-color: #0D81F2;
}
```

```
// xxx.js
import prompt from '@system.prompt';

export default {
  showDialog(e) {
    this.$element('simpledialog').show()
  },
  cancelDialog(e) {
    prompt.showToast({
      message: 'Dialog cancelled'
    })
  },
  cancelSchedule(e) {
    this.$element('simpledialog').close()
    prompt.showToast({
      message: 'Successfully cancelled'
    })
  },
  setSchedule(e) {
    this.$element('simpledialog').close()
    prompt.showToast({
      message: 'Successfully confirmed'
    })
  }
}
```

![](figures/GIF6.gif)
