# 香菇主页

香菇编写的个人导航主页，因为有些朋友想要源码，虽然是纯静态页面可以直接Ctrl+S，但为了方便分享，特在此处开源。

# 文件结构

```
(root)/
├─ icons/
│  ├─ *.jpg
│  ├─ *.png
│  ├─ *.svg
│  ├─ …
├─ src/
│  ├─ jquery.min.js
│  ├─ qrcode.js
│  ├─ are_you_ready.ogg
│  ├─ miao_cocoa.ogg
│  ├─ mao.svg
│  ├─ loading.svg
│  ├─ qrcode.png
│  ├─ favicon.png
│  ├─ 22.png / xiaobing.gif / xiaobing2.gif
├─ links.json
├─ index.html
```

# 部署方法

克隆项目或下载zip包解压到网站根目录即可访问。

# 使用说明

## 进入导航

点击`LET'S GO!`链接或调用`swLinks(1)`函数

## 搜索框

输入关键字自动匹配已有链接的名称、描述、地址，默认响应延时500毫秒

输入关键字后按回车使用搜狗搜索、按下方向键使用bing搜索……此功能可在JavaScript代码中`$('#search')...keydown`处自定义配置

## 链接点击操作

鼠标单击或触屏点击图标即可跳转网页或执行代码

鼠标右击或触屏长按可调出二维码，点击空白部分关闭二维码

## Hash直达功能

`#link`：自动跳转到链接页面，如：
https://siitake.cn/#link

`#search`：自动打开搜索框，如：
https://siitake.cn/#search

# 相关设置

## links.json 文件

links.json 是用来存放所有导航链接的文件，遵循json语法，下面解释文件中出现的key：

`name`：链接名称

`href`：链接地址或其他字符串

`desc`：链接描述显示在名称下一行

`logo`：链接图标，站点目录图片或远程URL均可，值为`null`则调用`src/loading.svg`

`func`：自定义函数代码，点击链接时执行，此时`n`(name)，`h`(href)，`d`(desc)，`l`(logo)可作为变量调用

`noUtm`：添加此key则链接跳转时不带utm参数

## 首页信息

标题(SIITAKE)名称在CSS(style)中`.logo::before`处修改

鼠标移动到标题上显示的表情包在CSS(style)中`.logo::after`处修改，`src`目录中提供了`22.png`，`xiaobing.gif`，`xiaobing2.gif`三个图片可选

## 链接随机顺序显示

取消掉JavaScript代码中`links.sort(function(){ return 0.5 - Math.random() });`的注释即可

# 引用素材说明

## 音频

`are_you_ready.ogg`：没错！就是你！准备好了吗？
来源：【泠鸢】交织together【单人版】(https://www.bilibili.com/video/av15770997)

`miao_cocoa.ogg`：喵~
来源：点击领取你的猫娘女友！总有一款适合你！~(https://www.bilibili.com/video/av55305494)

## 图片

`22.png`：来自bilibili表情包2233娘形象

`xiaobing.gif`，`xiaobing2.gif`：来自必应搜索中文站小冰形象

`mao.svg`：躲猫猫的「猫猫」形象出自游戏「Don't catch Cats」(https://apps.apple.com/app/dont-catch-cats/id1375311035)
