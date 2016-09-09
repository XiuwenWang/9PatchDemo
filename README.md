# Android中.9图片含义及制作教程
[个人主页](http://www.jianshu.com/users/64f479a1cef7/latest_articles)
[演示Demo下载](https://github.com/PingerWan/9PatchDemo)
 
---

### 一、[9patch](http://baike.baidu.com/link?url=hIV5poUxtU0ntjDyEZxxkB0IIKeiIEU5XIrIVisfOZjbifl1X4ayg_SU8NbXn3Hy6M_3AD9rn-4PDYhX8eC9sa)图片的概念

* [9patch](http://baike.baidu.com/link?url=hIV5poUxtU0ntjDyEZxxkB0IIKeiIEU5XIrIVisfOZjbifl1X4ayg_SU8NbXn3Hy6M_3AD9rn-4PDYhX8eC9sa)图片是andriod app开发里一种特殊的图片形式，文件的扩展名为：.9.png


* 9patch图片的作用就是在图片拉伸的时候保证其不会失真。所以我们使用.9图片，让图片在指定的位置拉伸和在指定的位置显示内容，这样图片的边边角角就不会出现失真了。


### 二、使用.9图片和不使用的差异
* [9patch](http://baike.baidu.com/link?url=hIV5poUxtU0ntjDyEZxxkB0IIKeiIEU5XIrIVisfOZjbifl1X4ayg_SU8NbXn3Hy6M_3AD9rn-4PDYhX8eC9sa)和一般图片的区别在于.9图片有四条黑边，而一般的图片没有，这四条黑边就是用来拉伸和指定显示位置的。

* 使用.9图片后，整个图片应该是包裹着你想要显示的内容的，而没有使用的话整个控件布局看起来特别糟糕。


![使用.9图片](http://upload-images.jianshu.io/upload_images/2786991-7641688c3314509c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![不使用.9图片](http://upload-images.jianshu.io/upload_images/2786991-c63c5a22202cbf05.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


### 三、绘制.9图片
* 绘制之前先来说一下.9图片的四条黑边的意义，每条黑边的意义都不一样。

> 顶部：在水平拉伸的时候，保持其他位置不动，只在这个点的区域做无限的延伸（拷贝）

> 左边：在竖直拉伸的时候，保持其他位置不动，只在这个点的区域做无限的延伸（拷贝）

> 底部：在水平拉伸的时候，指定图片里的内容显示的区域

> 右边：在竖直拉伸的时候，指定图片里的内容显示的区域


![绘制成图](http://upload-images.jianshu.io/upload_images/2786991-d0ddc81d9df022f9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


#### 1. 使用Eclipse工具制作.9图片
* 在Eclipse中有提供专门的工具来制作.9图片。在你的sdk目录下的tools目录下，有一个叫做draw9patch.bat的文件，双击打开就可以使用了。

![draw9patch工具图](http://upload-images.jianshu.io/upload_images/2786991-0b43797cbf9402fc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


* 打开之后，我们可以直接将图片拖动到该工具之中，或者点击File，然后在导入进来。


![导入普通png图](http://upload-images.jianshu.io/upload_images/2786991-0d511d84276b1a10.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

* 导入之后，我们可以看到左边是对图片的操作界面，右边则是实时的显示界面。接下来，我们要对图片进行描边了，描边之前一定要清楚四条边的含义，上左控制拉伸位置，下右控制内容显示位置。

* 描边时，按下鼠标左键，然后放在图片边界移动就能描边了，要是想要去掉黑边，可以按下Shift键，然后点击鼠标左键。

* 我们先绘制左上两边，控制拉伸位置，如下绘制完成了之后，可以看右边的阅览图，明显比没有绘制时边角的清晰度更高。

![绘制拉伸区域图](http://upload-images.jianshu.io/upload_images/2786991-083cf27a9cdedbb7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

* 绘制完了图片的拉伸区域之后，我们还需要绘制图片包裹的内容的显示区域，如果没有绘制的话，里边的内容是会从左到右依次显示，这样有时达不到我们想要的效果。

* Demo中的图片我想要图片里面的文本显示在中央区域，即不显示在文本区域，所以我的黑色描边可以这样描。

![绘制内容显示区域/完成图](http://upload-images.jianshu.io/upload_images/2786991-089a993c984542a1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 通过对四条边的描黑边处理，我们就成功了避免了使用图片时拉伸边角的问题，拉伸的都是我们设置的区域，显示的也是我们想要显示的位置。


#### 2. 使用Android Studio工具制作.9图片
* Android Studio中天生就自带了.9的绘制工具，你只需要将一般的png图片的名字末尾加.9后缀再拷贝到drawable目录下，然后点击打开就能进入.9图片的绘制工具。如果是一般的图片是不会打开.9绘制工具的。


![AS打开原图](http://upload-images.jianshu.io/upload_images/2786991-ea33798a77d24c4b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

* 接下的过程和在Eclipse的绘制过程是一模一样的，这里就不再继续演示了。绘制完成就可以直接使用了。


### 四、9patch图片使用总结
* 要想学会绘制.9图片一定要明白四条黑边的意义，还有一定要会使用draw9patch工具。

* 开发过程中，大部分的.9图片还是要我们程序员自己去绘制，当然你在公司的美工比较多的除外。所以学会绘制.9图片还是很重要的。

* 使用.9图片遇到错误千万别着急，先看一下错误提示，然后检查一下你绘制的图片有没有问题，实在解决不了可以发出来大家一起想办法。


### 五、关于在[Android Studio](http://www.android-studio.org/)中使用.9图片出错解决方案
* 用过[Android Studio](http://www.android-studio.org/)的童鞋都知道，AS中对.9的图片增加了安全检查机制，你的.9图片只要有不规范的地方都会给你编译报错，本人刚开始用AS时就深受其苦，后来才找到了解决办法。

* 解决方式主要有两种：
	* 一是让AS取消掉对.9图片的安全检查。找到你app目录下的build.gradle文件，打开之后你可以在buildToolsVersion属性之下添加取消安全检查的两行代码。
	
		    // 取消掉系统对.9图片的检查
		    aaptOptions.cruncherEnabled = false
		    aaptOptions.useNewCruncher = false
	* 二是 .9图片编译报错，那肯定说明你的.9图片制作不完善，你可以检查一下图片哪里没绘制好。你可以检查一下是否有重复绘制黑边，或者有哪条边没有绘制。这里注意：AS中要求.9图片的四条边都会绘制。

---
[个人主页](http://www.jianshu.com/users/64f479a1cef7/latest_articles)
[演示Demo下载](https://github.com/PingerWan/9PatchDemo)
####  以上纯属于个人平时工作和学习的一些总结分享，如果有什么错误欢迎随时指出，大家可以讨论一起进步。
