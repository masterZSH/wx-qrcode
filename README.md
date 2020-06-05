## 小程序二维码生成


## 使用

复制src/qrcode.js到小程序目录下，直接引入即可使用


## 方法说明

```js
// 通过RenderingContext绘制
function draw(ctx: any, options: any):void

// 根据id绘制 一般使用这个
function drawById(id: any, options: any):void

// 参数说明
/*
* @param ctx canvas RenderingContext实例，通过canvas.getContext('2d')返回
* @param id string "qrCode" cavans_id
* @param options object 选项
* @param options.text string  二维码内容
* @param options.width number 二维码的宽度
* @param options.height number 二维码高度
* @param options.correctLevel number 错误校正级别 级别越高 整体需要携带的信息越多：1可纠正约7%错误、0可纠正约15%错误、3可纠正约25%错误、2级别可纠正约30%错误。
默认为2
* @param options.background string color-string 背景颜色 默认白色"#ffffff"
* @param options.image object 二维码中加入图片
* @param options.image.x number 图片在canvas中的x轴坐标
* @param options.image.y number 图片在canvas中的y轴坐标
* @param options.image.width number 图片宽度 px
* @param options.image.height number 图片高度 px
* @param options.image.url string 图片地址 支持远程图片地址、本地图片地址、临时文件地址
*/



```









## 示例

1. 普通绘制

wxml
```html
<canvas style="width:128px;height:128px" type="2d" id="qrCode"></canvas>
```

js
```js
import {drawById} from "../tools/qrcode"
drawById.call(wx,"qrCode",{
    text:"666666"  , // 二维码内容
})
```

示意图
![图片](images/qrcode1.png)

代码片段
[地址](https://developers.weixin.qq.com/s/2UudNSm47bhF)


2. 控制二维码大小
wxml
```html
<canvas style="width:128px;height:128px" type="2d" id="qrCode"></canvas>
```

js
```js
import {drawById} from "../tools/qrcode"
drawById.call(wx,"qrCode",{
    text:"666666"  , // 二维码内容
    width:50,     // 宽度 px内容自动转换像素比
    height:50,    // 高度 
})
```
示意图
![图片](images/qrcode2.png)


[地址](https://developers.weixin.qq.com/s/y7uqzSmh77hi)




2. 加上图片
wxml
```html
<canvas style="width:128px;height:128px" type="2d" id="qrCode"></canvas>
```

js
```js
import {drawById} from "../tools/qrcode"
drawById.call(wx,"qrCode",{
      text:"1233",
      image:{
        url:"/images/money.png", // 支持远程图片、本地图片、临时图片
        width: 81, // 图片宽度
        height:93  // 图片高度
      }
})
```
示意图
![图片](images/qrcode3.png)


[地址](https://developers.weixin.qq.com/s/CFuM8SmJ7Ehx)
















