> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [www.zcool.com.cn](https://www.zcool.com.cn/article/ZMTA5NjkwMA==.html)

> 也许是 2020 年全网最全的关于 iOS、Android 设计规范、适配总结文章, 资讯, 字点先生, 原创文章 站酷网, 中国设计师互动平台。

**本文 6000 字上下，反复校对 6 遍以上，初步阅读完大概需要 25 分钟，若是深入理解并完全吸收则建议 “先收藏再反复的品，细细的品”。希望对各位朋友有所帮助，不足之处望校正，祝阅读愉快。**

![](https://img.zcool.cn/community/0129d85e1efaeda80120a89531f401.gif)

双 20 年终究还是来了，互联网产品对于这个时代不是什么新鲜事了，互联网人也从未停止对优秀产品的探索和创新。而做为一个设计人的我们，在前行的脚步中也应该温故知新，就让我跟大家一起来对 iOS、Android 的设计规范、适配问题做一次全面的梳理和复习吧。

**iOS 设计规范**  

苹果自 07 年 1 月 9 日正式发布 iPhone 到目前为止的 iPhone11Pro Max，已经历了十三代产品。19 年 9 月 11 日推出的 11、11Pro、11Pro Max 并没有新增尺寸，所以对设计师而言也就没有额外新增工作量了，还是按照以前的做法：750*1334px（@2x）或（375*667pt，@1x）做设计稿，再提供 @2x、@3x 切图。  

以下为苹果手机历代产品明细（话说你拥有过那几代产品，欢迎留言交流）  

一代：iPhone

二代：iPhone3G

三代：iPhone3GS

四代：iPhone 4

五代：iPhone 4s

六代：iPhone 5

七代：iPhone 5s、iPhone 5c

八代：iPhone6、iPhone6 Plus

九代：iPhone 6s、iPhone 6s Plus

十代：iPhone7、iPhone7 Plus

十一代：iPhone8、iPhone8 Plus、iPhone X

十二代：iPhone XS、iPhone XS Max、iPhone XR

十三代：iPhone11、iPhone11Pro、iPhone11Pro Max

**如何有效记住 iOS 设计规范，这里我总结了一个方法 “iOS 五点两图记忆法”，也就是五个点 + 两张图。**

1、设计尺寸：375x667pt @1x（750x1334px @2x）为基准设计。

2、设计工具：Sketch、Adobe XD、Photoshop

3、预览效果：Sketch Mirror、Adobe XD 或 Ps Play

4、切图输出：@2x @3x 两套

5、标注工具：蓝湖，摹客

![](https://img.zcool.cn/community/01c4485e3159c6a8012165185fbc7e.jpg)

![](https://img.zcool.cn/community/01a37c5e1f05fca8012165189a491a.jpg)

两图 psd 下载链接：[https://pan.baidu.com/s/15g2x0vDd1yZevADuUj1V3g](https://pan.baidu.com/s/15g2x0vDd1yZevADuUj1V3g) 提取码: i4ai

**考考你：**

1、iPhone8 尺寸的设计稿如何快速变成 iPhoneX 的设计稿？

2、@2 倍图被当作 @3 倍进行开发，会导致什么样的后果？

3、为什么要用 375x667pt @1 倍图进行设计？（后文也有详细答案哦）

4、iPhone8 显示为 34px 的文字在 iPhone11 pro Max 里面是不是也是 34px？

这里我们首先重点理解下 PX 和 PT 这两个单位， 弄清楚为什么建议使用一倍图进行 UI 设计，才能在设计中以不变应万变。（说明：该部分内容优化自静电老师的总结。公众号 @静 Design）

PX 大家可能比较熟悉，就是像素，英文 pixel 的简称。最通俗的理解就是找一个放大镜（不是电脑中的放大镜，是真实的放大镜），然后对准自己面前的显示器或者手机屏幕观看，大部分显示器会在放大镜下出现一个个点。这就是我们平时所说的像素概念。在一台物理分辨率为 1080x1920px 的显示器中，横向分布 1920 个点，纵向则有 1080 个点。这些点通过显示器的光学特性，为我们组成不同的图像。

![](https://img.zcool.cn/community/01f1565e1f06bfa80120a8958632d6.png)

请注意， 在不同尺寸的显示器上，这些点的单位面积并不是一样的。比如一台 22 英寸的 1080p 液晶显示器与一台 27 英寸的 1080p 液晶显示器，可以发现这两台显示器的像素分布就是 27 英寸的显示效果明显逊于 22 英寸显示器的效果，一个重要的原因就是两台液晶面板中的 “像素” 颗粒大小不一。

由此可见，像素这个单位是一个相对单位，不能用厘米、毫米等这些绝对度量单位来衡量他的长度或者宽度，因为 1 像素只代表一个单位的 “点”。

另一个重要单位是 PT，英文 point 的简称，这个单位也是 iOS 开发过程中使用的单位，与 px 这样的相对单位不同，PT（Point）是一个绝对单位，中文名字是 “磅因（或者磅）”（1PT=1/72 英寸）。

同样用简单直观的例子来演示，拿两台不同型号的 iPhone，比如一台 ip11 和一台 ip11pro Max，打开同样一款应用（如 QQ 音乐），准备好一把尺子，使用尺子分别测量最上方 title“音乐馆”文字尺寸。经测量，可以发现不同型号的 “音乐馆” 文字的尺寸都一样。也可以请 iOS 开发人员分别写两个针对不同尺寸机型适配的同一个文件，并在两部手机安装，确保这个文件中的字体使用一个字号（30PT）。在两个手机中运行并用尺子测量，我们发现他们的物理尺寸完全一样。

![](https://img.zcool.cn/community/0119df5e1f06d7a801216518f5eb43.png)

请大家记住一点，px 是相对单位，pt 为绝对单位（类似单位为厘米，毫米等等）。在不确定屏幕密度的情况下，px 与 pt 没有任何可比性。

在开发工程师眼中，你如果使用 750px 的分辨率作图，那么按原大小标注设计稿中的尺寸的话，他们同样在开发环境中是要换算为一倍尺寸的，比如你标注了字号为 40px，那么最终开发工程师写在代码里的就是 20pt，除以 2 的关系。但是呢，如果使用一倍基准分辨率作图，那么就不用除以 2 啦，所有尺寸开发工程师直接拿过去随取随用。

sketch 作为一款纯矢量的移动端 ui 设计软件，不管是设计还是后期与开发工程师的配合，都严格遵从开发原理，这种设计方法可以最大限度保证设计稿的复现，同时也可以减小文件体积和系统资源消耗，不管是从哪个方面看，都是设计师制作 ui 界面的明智之选。

最后总结一下原因，设计师使用一倍基准尺寸作图，主要是单位转换方便，输出切图方便，理解简单。对于工程师，他们不用再进行复杂的换算，有助于完美复现设计稿。

我们继续熟悉 iOS 中一些必不可少的页面规范细则。

**一、引导页**

引导页是一张完整图，不能适配，因此需要单独出设计图，iOS 共需提供 6 套尺寸，当然也支持视频形式。（目前 5 以下的适配基本淘汰）  

![](https://img.zcool.cn/community/01fd235e1f075ea80120a895ade75b.jpg)

**二、图标**

以 1024x1024px 尺寸进行图标创作即可。再通过现成尺寸模版资源，一键生成整套尺寸导出即可。（模版链接：https://developer.apple.com/design/resources/Template-AppIcons-iOS）  

注意：最终提交给到程序员的切图是直角，非圆角图标。

![](https://img.zcool.cn/community/010e655e1f07aaa801216518dde66d.png)

![](https://img.zcool.cn/community/01e3605e1f07aaa80120a895022fa5.jpg)

<table><tbody><tr><td><section><strong>设备名称</strong></section></td><td><section><strong>应用图标</strong></section></td><td><section><strong>App Store</strong> &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; <strong>图标</strong></section></td><td><section><strong>Spotlight</strong> &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; <strong>图标</strong></section></td><td><section><strong>设置图标</strong></section></td></tr><tr><td><section>iPhone11P, 11P Max, X,&nbsp;Xs, 8P , 7P , 6s P , 6P</section></td><td><section>180 x 180 px</section></td><td><section>1024 x 1024 px</section></td><td><section>120 x 120 px</section></td><td><section>87 x 87 px</section></td></tr><tr><td><section>iPhone11, XR, 8, 7, 6s, 6, SE，5s, 5c, 5,4s, 4</section></td><td><section>120 x 120 px</section></td><td><section>1024 x 1024 px</section></td><td><section>80 x 80 px</section></td><td><section>58 x 58 px</section></td></tr><tr><td><section>iPhone 1, 3G, 3GS</section></td><td><section>57 x 57 px</section></td><td><section>1024 x 1024 px</section></td><td><section>29 x 29 px</section></td><td><section>29 x 29 px</section></td></tr><tr><td><section>iPad Pro 12.9, 10.5</section></td><td><section>167 x 167 px</section></td><td><section>1024 x 1024 px</section></td><td><section>80 x 80 px</section></td><td><section>58 x 58 px</section></td></tr><tr><td><section>iPad Air 1 &amp; 2, Mini 2 &amp; 4,3 &amp; 4</section></td><td><section>152 x 152 px</section></td><td><section>1024 x 1024 px</section></td><td><section>80 x 80 px</section></td><td><section>58 x 58 px</section></td></tr><tr><td><section>iPad 1, 2, Mini 1</section></td><td><section>76 x 76 px px</section></td><td><section>1024 x 1024 px</section></td><td><section>40 x 40 px</section></td><td><section>29 x 29 px</section></td></tr></tbody></table>

其他设备图标尺寸

**三、状态栏和导航栏（具体尺寸见五点二图）**

状态栏：显示时间、运营商信息、电池电量等信息区域。(齐刘海区域)

导航栏：状态栏下面的区域，含页面标题、功能图标等信息区域。

状态栏跟导航栏一般会进行一体化设计。现在流行大标题导航栏设计，也就是加大导航栏的高度，融入页面内容的标题，当内容上滑时，大标题再回归到常规导航高度。（大标题导航栏的高度一般为 116pt（232px），这里包括了 20pt（40px）状态栏的高度，同时也能放得下 34pt（68px）的大标题和辅助信息（如返回等图标）。

![](https://img.zcool.cn/community/01ad3e5e1f07cea801216518f1a55d.png)![](https://img.zcool.cn/community/01f03f5e1f07cea80120a895ad47da.png)

  

导航栏中的元素必须遵守如下几个对齐原则:

1、返回按钮必须在左边对齐。

2、当前界面的标题必须在导航栏正中。（可无）

3、其他控制按钮必须在右边对齐。

**四、标签栏（具体尺寸见五点二图）**

标签栏：即 Tab 栏，为底部快速入口，iOS 规范中 Tab 栏一般有五个、四个、三个图标的形式。分为 “纯图标标签” 和“图标加文字标签”两种形式。

![](https://img.zcool.cn/community/0126ee5e1f07f4a8012165180271e9.png)![](https://img.zcool.cn/community/01230d5e1f07f5a80120a895d6d0ed.png)

  

**五、iTunes 上传页面**

在程序上传 App Store 时我们需要提供多张 App 截图，供用户了解 APP 的功能。这里我们需要提供 1242 x 2688px 和 1125 x 2436px 两套截图。也支持视频形式。（微信目前采用的是五张静态页面形式）

![](https://img.zcool.cn/community/01535c5e1f083ca80120a895ee9259.jpg)微信 iTunes 上传用截图

**六、 字体**

中文字体：PingFang SC，英文字体：SF UI Text 、SF UI Display，其中 SF UI Text 适用与小于 19pt 的文字，SF UI Display 适用于大于 20pt 的文字。

链接: https://pan.baidu.com/s/17cKM9co53TEN85gj4vy5dw 提取码: hd35

**七、色彩**

在 iPhone 上显示的色域要比我们作图时的 RGB 色域要广。所以在 iPhone 上设计怎样的颜色都可以，只要符合产品气质并且在色彩心理学理论范围内。官方建议的系统色彩如下：

![](https://img.zcool.cn/community/01dcd45e1f0866a801216518ad6ae1.png)iPhone 的系统色  

**八、控件**

控件包括：输入框、按钮、滑杆、页卡、开关等，在设计模板中已经全部列出。（下载地址：[https://developer.apple.com/design/resources/](https://developer.apple.com/design/resources/)）为了让设计更符合整体产品品牌调性，这些控件可以做二次设计。

但得注意两件事：第一，点击区域基本符合 44pt（88px）原则，也就是在手机上大小大概是 7mm-9mm，适合手指点击。第二，要设计操作的不同状态，不要只设计一种状态。

![](https://img.zcool.cn/community/011bbf5e1f0881a8012165189f6170.png)

默认控件

**控件中无处不在的 44pt（88px）**

之前我们介绍过，人手指点击区域为 7mm - 9mm，在 @2x 中就是 44pt（88px）。苹果的导航条、列表、工具栏都充满了 44pt（88px）这个神秘数字。我们在设计时一定也要考虑到手指的点击区域。  

![](https://img.zcool.cn/community/0106735e1f08a0a801216518be5ca0.png)

 无处不见的 44pt（88px）

**九、界面设计原则**

**1. 边距和间距（@2x）**

在移动端页面的设计中，页面中元素的边距和间距的设计规范是非常重要的，一个页面是否美观、简洁、通透和边距、间距的设计规范紧密相连。

（1）全局边距（iOS13，@2x）  

全局边距是指页面内容到屏幕边缘的距离，整个应用的界面都应该以此来进行规范，以达到页面整体视觉效果的统一。在实际应用中应该根据不同的产品气质采用不同的边距，让边距成为界面的一种设计语言，全局边距的设置可以更好的引导用户竖向向下阅读。还有一种是不留边距，通常被应用在卡片式布局中图片通栏显示，这种图片通栏显示的设置方式，更容易让用户将注意力集中到每个图文的内容本身。

![](https://img.zcool.cn/community/0102be5e1f08cda801216518078bb8.jpg)![](https://img.zcool.cn/community/01384c5e1f08cda80120a89509876a.jpg)

iOS 原生态页面 “设置” 和“通用”页面的边距都是 40px。（@2x）

![](https://img.zcool.cn/community/0142b25e1f08eca801216518be2068.jpg)

![](https://img.zcool.cn/community/012a8d5e1f08eda80120a895df19af.jpg)

微信和支付宝的边距都是 32px。（@2x）

（2）卡片间距

在移动端页面设计中卡片式布局是非常常见的布局方式，至于卡片和卡片之间的距离的设置需要根据界面的风格以及卡片承载信息的多少来界定，通常最小不低于 16px，过小的间距会造成用户紧张情绪，使用最多的间距是 20px、24px、30px、40px，当然间距也不宜过大，过大的间距会使界面变得松散，间距的颜色设置可以与分割线一致，也可以更浅一些。

以 iOS（750*1334px）为例，设置页面卡片间距为 70px，而通知中心承载了大量的信息，因此采用了较小的 16px 作为卡片的间距。

![](https://img.zcool.cn/community/01e9015e1f0907a80121651807b915.jpg)

![](https://img.zcool.cn/community/015f565e1f0908a80120a89556be75.jpg)

总结：卡片间距的设置是灵活多变的，一定要根据产品的气质和实际需求去设置，平时也可以多截图测量一下各类 APP 的卡片间距都是怎么设置的，看的多了并融会贯通，卡片间距设置自然会更加合理，更加得心应手。

（3）内容间距

一款 APP 除了各种栏（状态栏、导航栏、标签栏、工具栏）和控件 icon，就是内容了，内容的布局形式多种多样，这里不去探讨内容具体应该如何去布局，我们来说一说内容的间距设置问题。

**格式塔邻近性原则：**

单个元素之间的相对距离会影响我们的感知，互相靠近的元素看起来属于一组，而那些距离较远的则自动划分组外。来看下图，左图中的圆在水平方向比垂直距离近，那么，我们看到了 4 排圆点，而右图则看成 4 列。

![](https://img.zcool.cn/community/016aae5e1f0936a8012165188ad7ad.jpg)

在 UI 设计中内容布局时，一定要重视邻近性原则的运用  

**2. 内容布局**

在 APP 的设计中内容的布局形式多种多样，这里介绍最常用的两种布局形式，列表式布局和卡片式布局。

（1）列表式布局

列表式布局方式非常普遍，随便打开一个 APP，基本都存在这种布局方式。特点在于能够在较小的屏幕中显示多条信息，用户通过上下滑动的手势能获得大量的信息反馈。这也是一种非常容易理解的展示形式。

（2）卡片式布局

这种布局形式相对灵活。其特点在于每张卡片的内容和形式相互独立，互不干扰，所以可以在同一个页面中出现不同的卡片承载不同的内容。卡片式布局相对时尚、前卫，很多 to C 产品经常用到。另外，双栏卡片的布局形式，也常见于以图片信息为主导的 App，例如一些商城的商品陈列页面。这种形式能在一屏里显示更多的内容（至少 4 张），同时，由于分开左右两栏的显示，用户可以更加方便地对比左右两栏卡片的内容。

**3. 界面图片设计比例**

在 UI 设计中，对于图片的尺寸和比例没有严格的规范，设计师往往凭借经验和感觉设置一个看起来不错的尺寸，但事实上我们是有章可循的。运用科学的手段设置图片的尺寸，可以获得最优的方案，常见的图片尺寸有 16:9、4:3、3:2、1:1 和 1:0.618（黄金比例）等。  

**4.APP 版式设计规范**

版式设计又叫做版面编辑，即在有限的版面空间里，将版面的构成要素（文字、图片、控件）根据特定的内容进行组合排列。一个优秀的排版要考虑到用户的阅读习惯和设计美感，在 UI 设计中版面设计的基础原则有哪些呢？

（1）对齐

对齐是贯穿版式设计最基础，最重要的原则之一，它能建立起一种整齐规矩的外观，带给用户有序一致的浏览体验。

（2）对称

对称是对立统一规律的本质属性，呈现出一种和谐自然的美，在应用界面的设计中，引导页设计、注册登录输入框和按钮等无一不是对称的设计。

（3）分组

物以类聚，人以群分。分组是将同类别的信息组合在一起，直观的呈现在用户面前，这样的设计能够减少用户的认知负担，在移动端界面的设计中最常见的分组方式就是卡片，为用户选择提供专注而又明确的浏览体验。

**十、切图命名规范**

切图最后需要命名成规范格式，方便程序员查找。切图命名的格式建议全英文，如果大家英文不好需要想办法提升一点简单的词汇量。借由上述工具切图后，需要整理切图命名，或在切图之前对图层命名亦可。以下是切图元素的中英文对照：  

 ![](https://img.zcool.cn/community/010c295e1f09e8a80121651839746c.png)

切图命名对照表

然后我们要按照” 功能_类型_名称_状态 @倍数” 来命名每个切图，比如我们导航条上有一个搜索图标，那么它的名称就是： 

navi_icon_search_default@2x.png

(导航_图标_搜索_正常 @2x.png)

**Android 设计规范**

接下来，再一起来看看 Android 设计规范，这里只是把安卓规范中一些关键信息做了汇总，更详细的不过多赘述，网上已经有很多大佬产出过此类文章，大家可自行搜索。

**一、安卓开发单位是 DP、SP**

DP：安卓专用长度单位。

以 160 DPI 屏幕为标注，则 1DP=1PX

计算公式：dp x dpi/160=px

例：以 720x1280px （320dpi）为例， 1dp x 320 dpi/160=2px

SP：安卓专用字体单位。

以 160 DPI 屏幕为标注，则 1SP=1PX

计算公式：sp x dpi/160=px

例：以 720x1280px （320dpi）为例， 1sp x 320 dpi/160=2px

**  
二、安卓设计尺寸：以 1080x1920px 作为设计稿标准尺寸**

1. 从中间尺寸向上、下适配，界面调整幅度最小，最方便适配。

2. 大屏幕时代依然以小尺寸作为设计尺寸，会限制设计师的设计视角。

3. 用主流尺寸来做设计稿尺寸，极大的提高了视觉还原和其他机型适配。

![](https://img.zcool.cn/community/01e7055e1f0a09a801216518efd217.jpg)

**三、安卓图标尺寸**

![](https://img.zcool.cn/community/01229e5e1f0a30a8012165187b412c.png)

**四、安卓字体**  

中文：思源黑体 / Noto Sans Han

英文：Roboto

大小：主题文字 36-34px    正文 28-26px     提示文字 24-22px

链接: [https://pan.baidu.com/s/17cKM9co53TEN85gj4vy5dw](https://pan.baidu.com/s/17cKM9co53TEN85gj4vy5dw) 提取码: hd35

**  
五、切图规范**

1. 切图尺寸必须为双数

2. 单像素的图会出现边缘模糊的情况

一般情况下，我们只需要提供 3 套切图资源就可以满足安卓工程师的适配，分别是 HDPI、XHDPI、 XXHDPI 3 套切图资源。

**如何用 iOS 的设计稿适配安卓**

现在绝大多数公司限于人力物力的限制，不能把 iOS 和安卓的设计稿全部执行出来，因此就存在一稿两用的情况；设计师以 iOS 版本的设计稿来适配安卓，下面我们来看一组有趣的数学换算题：

1080/1.5=720，720/1.5=480，1242*2208/1.15=1080*1920，也就是说，1242*2208（iOS@3 倍尺寸）与 1080*1920（安卓尺寸）是可以等比缩放的，所以，iOS 与 Android 的尺寸是可共用 1242*2208px。因此，以 iOS 设计尺寸进行设计是可以适配 Android 的。（前提是必须和安卓工程师沟通清楚）

另一种方式，就是把 750×1334px 等比例调整尺寸到安卓 1080×1920px，对各个控件进行微调，重新提供标注（用 dp 标注）。也就是需要提供两套标注，一套给 iOS，一套给 Android。

**iOS 开发语言**

作为 iOS 开发工程师，最重要的三个工具是：Obiective-C、Swift、UIKit 框架。Obiective-C 是目前最有效率的语言；而 Swift 开发非常高效。一般 iOS 工程师会在这两个语言中选择一种作为开发工具。UIKit 是苹果系统自带的一套框架，这个框架里有设置按钮、滑竿、状态栏、电池电量、键盘等接口可供调用。所以我们看到很多第三方 APP 的界面中，有许多控件和苹果自带程序是一致的，这就是 UIKit 的功劳。

**  
iOS 开发里单位是 pt**

750×1334 尺寸的换算关系 1pt=2px，也就是说程序员拿到我们的 px 单位的标注稿，自己除以 2 就是 pt 了。（这也是为什么建议设计师用 @1 倍图做设计稿的原因）

**参考资料及资源下载**

苹果开发者中心网址：

[https://developer.apple.com/](https://developer.apple.com/)

苹果人机交互规范：

[https://developer.apple.com/design/human-interface-guidelines/](https://developer.apple.com/design/human-interface-guidelines/)

iOS 设计资源下载：

[https://developer.apple.com/design/resources/](https://developer.apple.com/design/resources/)

iOS 控件下载地址：

[https://developer.apple.com/design/resources/](https://developer.apple.com/design/resources/)

设计师必备 APP 字体包：

链接: [https://pan.baidu.com/s/17cKM9co53TEN85gj4vy5dw](https://pan.baidu.com/s/17cKM9co53TEN85gj4vy5dw) 提取码: hd35

屏幕尺寸规范资源：

[http://www.woshipm.com/screen/watch.html](http://www.woshipm.com/screen/watch.html)

PS 蓝湖插件下载：

[https://lanhuapp.com/ps](https://lanhuapp.com/ps) 

SKetch 插件下载：

[https://lanhuapp.com/mac](https://lanhuapp.com/mac)

蓝湖手机预览 APP 下载：

[https://lanhuapp.com/app](https://lanhuapp.com/app)  

蓝湖自动同步网盘团队协作：

[https://lanhuapp.com/sync](https://lanhuapp.com/sync)

我是 Piger，一个游走在设计行业十余年的设计人。我积累了很多 “无用功”，我将毫无保留的分享出来，与大家一同学习、进步。

整理不易，愿各位有所收获。

感谢！

2020.1.15

**你们的 “点赞”，是我继续前行的动力。**