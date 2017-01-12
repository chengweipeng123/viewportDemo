# viewportDemo

注1：测试使用iphone5s，iOS10.2，iOS内置UIWebView

注2：在移动开发中，

​	`visual viewport = window.innerWidth`, 

​	`laytout viewport = document.documentElement.clientWidth` 

注3：以下viewport衡量单位均为css pixel

1. 页面无meta viewport设置

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

   页面的放大，会改变的`Visual Viewport`值。响应的页面元素有缩放。

   页面元素css piexl的大小，与设备ScreenWidth值无关。

2. ​

3. ​