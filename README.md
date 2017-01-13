# viewportDemo

注1：测试使用iphone5s，iOS10.2，iOS内置UIWebView。

注2：在移动开发中，

​	`visual viewport = window.innerWidth`, 

​	`laytout viewport = document.documentElement.clientWidth` 

注3：以下viewport衡量单位均为css pixel

注4：CSS元素 默认字体为16px

注5：理想体验为：`idea viewport = visual viewport = layout viewport =screen.width`



1. **scalesPageToFit = NO**

   在iOS UIWebView默认情况下，scalesPageToFit为NO：

   ```
   ScreenWidth:320
   Visual Viewport Width:320
   Layout Viewport Width:320
   ```

   页面自动适配`Visual Viewport Width = Layout Viewport Width`，不可缩放。

   ​

2. **scalesPageToFit = NO，页面无meta viewport设置**

   ```
   <head>
        <meta http-equiv="Content-Type" content="text/html; charset=utf-8"/>
        <meta content="text/html;charset=utf-8" http-equiv="Content-Type">
   </head>
   ```

   页面初始：

   ```
   ScreenWidth:320
   Visual Viewport Width:980
   Layout Viewport Width:980
   ```

   当页面中无meta viewport设置时，可以看出，`Visual Viewport Width = Layout Viewport Width `，为一个默认	值**980** 。

   这种情况下，因为`Visual Viewport Width = Layout Viewport Width`，所以浏览器缩小了整个页面，即把width为980px缩小至屏幕320px，同时内部全部的字体内容等等都缩小，测试css 1

   ​

   放大页面：

   ```
   ScreenWidth:320
   Visual Viewport Width:493
   Layout Viewport Width:980
   ```

   页面的放大，会改变的`Visual Viewport`值。相应的页面元素有缩放。

   页面元素视觉上的大小，与设备ScreenWidth值无关，即其本身设置的css 元素大小与设备系统元素大小无关，只与设备默认layout viewport width相关。

   缩放值为：

   > 当前缩放值 = ideal viewport宽度  / visual viewport宽度，即320/980。

3. **scalesPageToFit = NO，增加meta viewport 设置**

   ```
   <head>
           <meta http-equiv="Content-Type" content="text/html; charset=utf-8"/>
           <meta content="text/html;charset=utf-8" http-equiv="Content-Type">
           <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes"/>
       </head>
   ```

   初始数据值：

   ```
   ScreenWidth:320
   Visual Viewport Width:320
   Layout Viewport Width:320
   ```

   这时候，达到的理想情况。

   此时，css的font-size因为`ScreenWidth=Layout Viewport Width`的原因，就会和手机系统的字体大小一致起来，也就是说，css里的16px字体与系统的16号字体一样大。