# HTML

## Day06_HTML与标签

### 网页

就是一个文件，不同的文件它的后缀名是不一样的，网页的后缀名htm或者html（标准），打开一个网页就是打开一个文件

![image-20230703202359888](img/image-20230703202359888.png)

### Html:超文本标记语言(标签)

<标签名字>

#### 标签：

1.双标签	
<开始标签></结束标签>

2.单标签 自结束标签
<标签名/>



快捷键：
	Ctrl+s保存

敲标签的时候  
	可以先敲标签名 在按tab键它会自动生成

标签是不区分大小写的，但是我们在写的时候尽量保持小写

`<!DOCTYPE html> 告诉浏览器我当前是html5的模板 你要以html5的模板来进行解析,如果不加 一些浏览器会以怪异模式解析  标准模式`



`<html lang='en'></html> 网页的起始和结束 html叫做根 标签 root`

`lang=’en’ 表示的当前的网页是英文的网页 浏览器在看到这个东西的时候它会出现翻译`

`lang=’en’ 英文网页`

`lang=‘zh-CN’ 中文网页`



`https://www.w3school.com.cn/tags/html_ref_country_codes.asp`



`<head></head> 网页的头部

<meta charset=’utf-8’/> 告诉浏览器以什么样的字符集来解析我这个文件

<title></title>  网页的标题  网站的名字

<body></body> 网页的主体区域`



如果说需要快速生成网页的模板 !（英文状态下的！） 回车

Html的规范  w3c机构指定

规则：你必须按照它的要求来   规范：约定俗成，所有程序员的一种默契

H1:标题标签 一级标题  双标签

H2:标题标签 二级标题  双标签

标题标签只有h1-h6 标题标签



用的多 h1-h3用的比较多，h1一个页面只能出现一次

#### P：段落标签

Strong：加粗标签 以加粗的形式突出内容的重要性

#### B：加粗标签  以样式的形式加粗

​	 他们的区别：

1. 再一些特殊的设备底下这个两个标签展示方式是不一样，如盲人阅读模式，strong语气会重，b就是正常语气
2. SEO搜索引擎优化的时候 strong容易被爬虫爬取



#### Em:

突出内容的重要性 斜体标签 以斜体的形式突出内容的重要性的

 

#### 语义化标签和非语义化标签

##### 语义化标签：

​	有含义的 语义化的标签并不是它的长相是如何的，而是它本身真正含义

​	代码可读性增强，给其它程序员看的

​	有利于seo优化

​	输出的效果也是比较特殊



##### 没有语义化的标签:

######  Div:

盒子标签，定义网页中的某一部分区域的，最终我们需要通过css来定义这个内容

###### Span:

定义一部分文本内容,也是后期通过样式来处理这一块文本内容

 

#### 其他一些标签

Sup:上标文字标签

Sub:下标文字标签

Del:删除文本标签

Ins:插入标签

U:下滑线标签

Code：代码标签

i: 斜体标签

cite:引用标签

small：附属标签,如:版权

bdo:文字方向标签 属性 dir:文字的方向  ltr: left to right 从左往右   rtl:从右往左

 

#### 总结需要记得内容:

h1-h6标题标签

P 段落标签

Strong ：以加粗的形式突出内容的重要性

Em:以斜体的方式突出内容的重要性



#### 代码的格式化操作

​	可以让代码看起来更加整齐

​	鼠标右键 

![image-20230703202007349](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20230703202007349.png)

#### 特殊符号:

​	再html种有一些东西浏览器解析出来是有问题，或者说跟我们想要的结果是不同的，可以使用特殊符号来代替

![image-20230703202419373](img/image-20230703202419373.png)

​	参考 https://blog.csdn.net/six6de6/article/details/125809517 

​	这些东西全部不需要记

 

Br:换行标签  单标签  单标签 /是写在结束位置<br/>

Hr:水平线标签  单标签 <hr/>

> 这里目前知道 但是有问题, 学了css以后再回过来总结

**P:目前里面除了p h1 div 不可以放放 其余的都可以放**

**Div:里面可以放任何东西**

**H1-h6里面它不可以放p 不可以放h1-h6 不可以放div 其余都可以**

> 其余的文本标签 可以放 除了p h1-h6 div以外的任何文本标签



#### 属性:

标签上有一些属性,不同的属性和不同的属性值 可以让这个标签起到的效果是不一样的，**属性的形式** key=value  **属性名=属性值** 属性值必须是双引号或者单引号 并且是英文状态的
	Age = 13



Img:图片标签  单标签
	Src:图片的地址

服务器地址：
	 <img src="http://t15.baidu.com/it/u=1799435314,1905157377&fm=224&app=112&f=JPEG?w=500&h=500"/>



绝对路径
<img src="C:\Users\stwd\Desktop\丁鹿学堂6月\day01\nhz.jpg"/>

相对路径
<img src="./thg.jpg"/>

> Width:图片的宽度
>
> Height：图片的高度  单位默认是px（像素）
>
> Title:鼠标放到该标签上的一个提示文字，可以再任何标签上使用
>
> Alt：图片加载失败时候的提示内容
>
> Video:视频标签
>
> Controls：视频播放控件
>
> Muted：静音属性
>
> Autoplay:自动播放,自动播放必须和静音一起使用，
>
> ​	原因：浏览器的安全限制
>
> Loop:循环播放
>
> Poster:视频的第一帧 第一帧的图片地址





## Day07_HTML标签2

### 注释

> 注释:不是给浏览器看的，放在注释里面内容浏览器不会解析,注释是给人看的，其实就相当于是一个备注

------



### 常用的快捷键



>   ctrl+s:保存
>
>   ctrl+c:复制
>
>   ctrl+v:粘贴
>
>   ctrl+x:剪切
>
>   ctrl+z:返回
>
>   ctrl+/:注释
>
>   ctrl+f:搜索
>
>   ctrl+enter 回车键 可以快速的换一行

------



### 音频标签

>   audio:音频标签
>
>   controls:音频播放器
>
>   muted:静音属性
>
>   loop:循环播放
>
>   音频标签基本数据和视频标签是类似的

```html
<audio src="./Sound of Silence.mp3" controls muted loop></audio>

```

------



### 超链接

> **a:超链接**
>
>    href:超链接的地址
>
>    target:超链接打开方式
>
> ​    _self:默认值，在当前的窗口打开
>
> ​    _blank:在新的窗口打开链接
>
> ​	title:鼠标放上后，显示的内容



> 跳转到**第三方页面**

```html
<a href="https://www.baidu.com" target="_blank" title="哈哈">百度</a>
```

> 跳转到**指定的页面** 

```html
 <a href="./success.html" target="_blank">跳转到登录成功页面</a>
```



> **download**:强制下载 如果说强制下载的时候 需要以服务的形式启动该项目
>
> 当我们使用live server打开当前的页面的时候,liveserve会帮我们在内存中
>
> 创建一台服务器 127.0.0.1:3000 ，它会模拟将我们的页面部署到服务器的效果

```html
<a href="./Katie Sky,Timeflies - Monsters.mp4" download="小电影"> 下载电影</a>
<a href="./Sound of Silence.mp3" download="好听的歌曲">下载音乐</a>
<a href="./nhz.jpg" download="小姐姐">下载图片</a>
<a href="./test.docx" download="不可描述的文件">下载文件</a>
<a href="./test.rar" download="不可描述的压缩包.rar">下载压缩包</a>
```



> **唤醒手机内部的一些功能**，还可以唤起一些app

> 打电话 tel: 固定格式 	号码些写什么就是打电话给什么

> 发邮件 mailto: 固定格式 	邮箱号写什么就是发给什么

```html
<a href="tel:10086">打电话</a>
<a href="mailto:123@qq.com">发邮件</a>
```

> **打开一些APP**，如微信，淘宝等，可能有些api打不开。
>
> **原因**
>
> ​	协议它是有白名单的，有些手机是不可以直接打开的，需要正式开发的时候是一个完整的地址
>
> ​    这个app的完整连接需要公司去申请对应id,领导做的,到时候我们前端只需要发起请求拿这个地址
>
> ​    就可以了，然后将这个地址放在超链接href里面就可以了
>
> ​    现在只需要做个了结就可以，就是超链接可以唤起对应app 然后给不同地址

```html
    <a href="weixin://">打开微信</a>
    <a href="alipayqr://platformapi/startapp">打开支付宝</a>
    <a href="taobao://">打开淘宝</a>
    <a href="mqq://">打开QQ</a>
```



### 超链接锚点

> ​	当超链接的地址是#xxx的时候,在点击的时候当前页面路径后面会匹配上#xxx。但是后续ID的属性值里面不带#，切记。
>
> ​	这个时候如果说页面中有id的名字和当前路径中#后面的内容是匹配的，那么id部分会来到当前网页的最前面
>
> ​	#xxx 它专业我们叫做hash

```html
  <a href="#one">第一章</a>
  <a href="#two">第二章</a>
  <a href="#three">第三章</a>
  
  <h2 id="one">这里是第一章内容的区域</h2>
 
  <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br> 
  <h2 id="two">这里是第二章内容的区域</h2>
 
  <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br> 
  <h2 id="three">这里是第三章内容的区域</h2>
```



### 锚点小案例

> 从页面A直接跳转到页面B的锚点部分

```html
<h1>我是第一个页面</h1>
<a href="./success.html#bd">到成功页面百度的答案</a>
<a href="./success.html#jd">到成功页面京东的答案</a>

<!--页面B -->
<p id="bd"></p>
<p id="jd"></p>
```







### 音频和视频标签问题

> 视频的格式有很多种
>
>    如：mp4  avi wmv mov rm flv
>
>    这个video标签它是h5中新增的标签,标签比较新,有一些浏览器可能没法去解析一些格式视频
>
>    举例:
>
> ​    A浏览器：可能支持mp4和avi 不支持其它的
>
> ​    B浏览器: 可能支持wmv mov 不支持 其它的
>
> ​    C浏览器：可能支持rm flv 其它的不支持
>
> ​    D浏览器: 可能支持mp4 flv 其它又不支持
>
> ​    如果说我们需要多个浏览器都支持，那么需要让后端准备多套视频,
>
> ​    ./Katie Sky,Timeflies - Monsters.mp4
>
> ​    ./Katie Sky,Timeflies - Monsters.avi
>
> ​    ./Katie Sky,Timeflies - Monsters.wmv
>
> ​    ./Katie Sky,Timeflies - Monsters.mov

```html
  <video controls muted>
    <source src="./Katie Sky,Timeflies - Monsters.aa"></source>
    <source src="./Katie Sky,Timeflies - Monsters.bb"></source>
    <source src="./Katie Sky,Timeflies - Monsters.cc"></source>
    <source src="./Katie Sky,Timeflies - Monsters.ddd"></source>
    <p>您的浏览器版本太低不支持视频播放，请升级 <a href="test.rar" download>下载</a></p>
  </video>

  <audio>
    <source src="xxx.xxx"></source>
    <source src="xxx.xxx"></source>
    <source src="xxx.xxx"></source>
  </audio>
```



### 有序列表和无序列表

>    ol: ordered lists 表示有序列表
>
>    li: list item 列表中的每一项 li是可以有多项的
>
>    有序列表是有顺序的，默认是以阿拉伯数字开头
>
> ​    type:列标签前面的符号是什么 A a I i 这个属性我们基本不用  前面的符号以后我们是会把它去掉的
>
>    除了ol li可以实现列表效果以外 其实很多的标签都可以用来实现列表效果
>
>    如果说我们注重语义化的那么就需要使用列表

```html
<ol type="1">
    <li>哈哈哈</li>
    <li>哈哈哈</li>
    <li>哈哈哈</li>
    <li>哈哈哈</li>
</ol>
```



> 无序列表
>
>   ul: unordered lists 无序列表
>
>   li: list item 列表中的每一项 li是可以有多项的
>
> ​    也可以通过type属性去修改它前面的符号 默认是实心圆 circle:空心圆  square:实心方块，基本不用

```html
<ul type="square">
    <li>宝马</li>
    <li>奔驰</li>
    <li>奥迪</li>
</ul>
```



> 这些列表中 ul中 除了放li 其余的标签都不要放
>
> li里面可以放任何标签

```html
<ul>
    <li><a href="">我是第一项</a></li>
    <li>我是第一项</li>
    <li>我是第一项</li>
    <li>我是第一项</li>
</ul>
```



### 列表的小案例

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>

<body>
  <ul>
    <li><a href="#info">个人信息</a></li>
    <li><a href="#record">个人履历</a></li>
    <li><a href="#video">自拍视频</a></li>
    <li><a href="#img">个人图片</a></li>
  </ul>

  <!-- 个人的信息  属性值如果是自己写内容 尽量不要使用中文 或者说数字开头-->
  <div id="info">
    <h2>个人信息</h2>
    <p>
      姓名:刘德华 &nbsp;&nbsp;&nbsp;
      性别:男
    </p>
    <p>
      邮箱:12312@qq.com
    </p>
    <p>
      号码:13412341234
    </p>
    <p>
      职业:歌手
    </p>
  </div>
  <!-- 个人履历 -->
  <div id="record">
    <h2>个人履历</h2>
    <ul>
      <li>
        <h3>1993-2-2发生了什么事情</h3>
        <p>
          不瞒大不瞒大家说，杨超越女士的私服穿搭一直是我学习借鉴的榜样，她的穿搭，不会刻意用大牌提高身价，不会为了秀身材选择暴露的单品家说，杨超越女士的私服穿搭一直是我学习借鉴的榜样，她的穿搭，不会刻意用大牌提高身价，不会为了秀身材选择暴露的单品。
        </p>
      </li>
      <li>
        <h3>1993-2-2发生了什么事情</h3>
        <p>
          不瞒大不瞒大家说，杨超越女士的私服穿搭一直是我学习借鉴的榜样，她的穿搭，不会刻意用大牌提高身价，不会为了秀身材选择暴露的单品家说，杨超越女士的私服穿搭一直是我学习借鉴的榜样，她的穿搭，不会刻意用大牌提高身价，不会为了秀身材选择暴露的单品。
        </p>
      </li>
      <li>
        <h3>1993-2-2发生了什么事情</h3>
        <p>
          不瞒大不瞒大家说，杨超越女士的私服穿搭一直是我学习借鉴的榜样，她的穿搭，不会刻意用大牌提高身价，不会为了秀身材选择暴露的单品家说，杨超越女士的私服穿搭一直是我学习借鉴的榜样，她的穿搭，不会刻意用大牌提高身价，不会为了秀身材选择暴露的单品。
        </p>
      </li>
      <li>
        <h3>1993-2-2发生了什么事情</h3>
        <p>
          不瞒大不瞒大家说，杨超越女士的私服穿搭一直是我学习借鉴的榜样，她的穿搭，不会刻意用大牌提高身价，不会为了秀身材选择暴露的单品家说，杨超越女士的私服穿搭一直是我学习借鉴的榜样，她的穿搭，不会刻意用大牌提高身价，不会为了秀身材选择暴露的单品。
        </p>
      </li>
    </ul>
  </div>
  <!-- 自拍视频 -->
  <div id="video">
    <h2>mv视频</h2>
    <div>
      <video src="./Katie Sky,Timeflies - Monsters.mp4"></video>
      <p>这是一个我跳舞的视频</p>
    </div>
    <div>
      <video src="./Katie Sky,Timeflies - Monsters.mp4"></video>
      <p>这是一个我跳舞的视频</p>
    </div>
  </div>
  <!-- 个人图片 -->
  <div id="img">
    <h2>图片区域</h2>
    <img src="https://img1.baidu.com/it/u=3362992399,3841187123&fm=253&app=138&size=w931&n=0&f=JPEG&fmt=auto?sec=1688576400&t=9c0cf1ed7ada10cf748384c7ede7e7b1" width="300" height="300">
    <img src="https://img1.baidu.com/it/u=3362992399,3841187123&fm=253&app=138&size=w931&n=0&f=JPEG&fmt=auto?sec=1688576400&t=9c0cf1ed7ada10cf748384c7ede7e7b1" width="300" height="300">
    <img src="https://img1.baidu.com/it/u=3362992399,3841187123&fm=253&app=138&size=w931&n=0&f=JPEG&fmt=auto?sec=1688576400&t=9c0cf1ed7ada10cf748384c7ede7e7b1" width="300" height="300">
    <img src="https://img1.baidu.com/it/u=3362992399,3841187123&fm=253&app=138&size=w931&n=0&f=JPEG&fmt=auto?sec=1688576400&t=9c0cf1ed7ada10cf748384c7ede7e7b1" width="300" height="300">
    <img src="https://img1.baidu.com/it/u=3362992399,3841187123&fm=253&app=138&size=w931&n=0&f=JPEG&fmt=auto?sec=1688576400&t=9c0cf1ed7ada10cf748384c7ede7e7b1" width="300" height="300">
    <img src="https://img1.baidu.com/it/u=3362992399,3841187123&fm=253&app=138&size=w931&n=0&f=JPEG&fmt=auto?sec=1688576400&t=9c0cf1ed7ada10cf748384c7ede7e7b1" width="300" height="300">
    <img src="https://img1.baidu.com/it/u=3362992399,3841187123&fm=253&app=138&size=w931&n=0&f=JPEG&fmt=auto?sec=1688576400&t=9c0cf1ed7ada10cf748384c7ede7e7b1" width="300" height="300">
  </div>
</body>

</html>
```



### 自定义列表

dl: definition lists 自定义列表 又可以有多组dt和dd的组合 相对来说网页中 用的越来越少了

   dt: definition term 列表的标题

   dd: definition description 列表的每一项

   dt是配合dd一起使用  一个dt标题下面可以有多个dd

```html
<dl>
    <dt>逃学威龙</dt>
    <dd>导演:王晶</dd>
    <dd>主演:周星驰</dd>
    <dd>配角:吴孟达</dd>
    <dt>英雄本色</dt>
    <dd>导演:王晶</dd>
    <dd>主演:周星驰</dd>
    <dd>配角:吴孟达</dd>
</dl>
```



### 表格

> ​	**如果说标签或者说属性鼠标放上去没有任何提示内容出来，该标签或者该属性就是废弃的属性。或者说这些属性已经不推荐使用了。**



> table:表格标签 
>
> ​	caption：表格的标题
>
> ​	thead:表格的头
>
> ​	tbody:表格的主体
>
> ​	tfoot:表格的脚步 底部
>
> ​	tr: table row 表格的行
>
> ​	th: table header cell 表格的标题单元格
>
> ​	td: table data cell 行中单元格 
>
> ​		colspan:跨列 水平方向跨列 
>
> ​		rowspan：跨行属性

​	

> table的属性
>
> ​    属性：
>
> ​    border:边框(废弃) 
>
> ​    width:'表格的宽度'
>
> ​    cellspacing：表格单元格之间的距离 
>
> ​    cellpadding：单元格离内部内容之间距离
>
> ​    align：表格整体位置 （废弃）
>
> ​    	 如果用整个表格身上表示的整张表格的对齐方式 如果是用在某一部分的 某一部分内容的对齐方式
>
> ​    	 left:居左
>
> ​    	 center:居中
>
> ​    	 right：居右

```html
<table border width="800" height="300" cellspacing="0" cellpadding="20">
    <caption>xxx班级信息</caption>
    <thead height="80">
      <tr>
        <th>名字</th>
        <th>年龄</th>
        <th>性别</th>
        <th>备注</th>
      </tr>
    </thead>
    <tbody align="center">
      <tr>
        <td>张三</td>
        <td>13</td>
        <td>男</td>
        <td rowspan="3">备注的内容有很多的文字</td>
      </tr>
      <tr>
        <td>李四</td>
        <td>14</td>
        <td>女</td>
      </tr>
      <tr>
        <td>王五</td>
        <td>15</td>
        <td>女</td>
      </tr>
    </tbody>
    <tfoot height="50">
      <tr>
        <td colspan="4">统计人数:3</td>
      </tr>
    </tfoot>
</table>
```

