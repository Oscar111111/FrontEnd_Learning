# CSS

## Day09_CSS基本介绍

### CSS的写法

> ​	**Cascading Style Sheets**：层叠样式表。用来给网页装修，美化HTML,美化结构的颜色，大小，位置，动画...



#### 	行内样式

> 行内样式（内联样式）
>
> > ​     行内样式就是将css写入标签
> >
> > ​     样式的结构是 **key:value** 的形式
> >
> > > ​     	key:属性(单词的形式)  value:属性值



> **语法**：
>
> color:字体颜色
>
> font-size:字体大小 单位是px像素

```html
<h1 style="color:red;font-size: 60px;">我是一个标题</h1>
```



> **行内样式缺陷**:
>
> ​    1.它的写法是跟html(结构)写再一起的，最终可能会导致整个页面及其混乱 不利于以后的维护
>
> ​    2.一些样式不能复用(反复使用),相同的样式需要反复的书写
>
> ​    注：虽然有缺陷，但是我们偶尔也会去使用,简单样的样式会去使用 但是不要出现大幅的使用

------



#### 	内部样式

> 它是书写在style标签之间的

      <style></style> 样式标签 专门用来书写css

> 它可以放在当前文档的任何一个位置，但是我们基本上会把这个标签放到head里面



> 语法:
>
> 注：h1选择器  {}样式代码块  color:样式属性  red:样式值
>
> 选择器：选中你要修改样式的那个标签

```html
        <style>
          h1{color: red;font-size: 50px;}
          p{color: blue;font-size: 60px;}
        </style>
```



> **优点:**
>
> ​	结构和样式分离，方便后期维护

------



#### 	外部引用样式（用的最多）

> 写一个文件 **.css**后缀名结尾
>
>    该文件内的样式写法和内部样式写法是一模一样的
>
>    需要使用link标签引入这个文件才能起到效果

   

```html
<link rel="stylesheet" href="./index.css">
```

> **link**:
>
> ​     引入外部资源  
>
> ​     rel：关联,
>
> ​     stylesheet：表示当前的link标签关联的是一个样式表  样式文件
>
> ​     href:'文件的路径'

​	

> **优点**:
>
> ​    结构和样式彻底分离成为不同的文件
>
> ​    并且可以复用文件

------



### CSS的选择器

> 选择器:
>
> ​	选中对应的标签来修改样式



#### 标签选择器

> 直接拿标签名来当选择器 它叫标签选择器。

```html
<style>
	h1{
      color: red;
      font-size: 40px;
    }
</style>

<h1>我是一个标题</h1>
```

------



#### id选择器

> 在标签上添加id='xxx' 这个id就可以用来当做选择器 这种选择器我们叫id选择器
>
> css选中这个id  #id名 
>
> **id开头的值不能为数字，貌似只能为字母？（待验证）**

```html
<style>
	#one{
      color: red;
      font-size: 40px;
    }
</style>

<h1 id="one">我是一个标题</h1>
```

------



#### 类选择器

> 在标签上加一个class='xxx' css在选择这个类名的时候.类名
>
> **class开头的值不能为数字，貌似只能为字母？（待验证）**
>
> > ​	这种选择器 类选择器
> >
> > > ​		1.特点 类名可以重复
> > >
> > > ​		2.一个标签可以有多个类名

```html
<style>
	.one{
      color: red;
      font-size: 40px;
    }
</style>

<h1 class="one">我是一个标题</h1>
```

------



### 课堂小案例

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=, initial-scale=1.0">
    <title>CV</title>
    <!-- CSS -->
    <style>
        .Character1 {
            color: #4285F4;
            font-size: 50px;
            font-family: 'Roboto', sans-serif;
            font-weight: 900;
        }

        .Character2 {
            color: #EA4335;
            font-size: 50px;
            font-weight: 900;
        }

        .Character3 {
            color: #FBBC05;
            font-size: 50px;
            font-weight: 900;
        }

        .Character4 {
            color: #4285F4;
            font-size: 50px;
            font-weight: 900;
            background-color: #EA4335;
            width: 200;
        }

        .Character5 {
            color: #34A853;
            font-size: 50px;
            font-weight: 900;
        }

        .Character6 {
            color: #EA4335;
            font-size: 50px;
            font-weight: 900;
        }

        .newstitle {
            color: #FF0000;
            font-size: 24px;
            font-weight: 900;
        }

        .subtitle {
            color: #e2980d;
            font-size: 14px;
            font-weight: 900;
        }

        .source {
            color: rgb(7, 245, 38);
            font-size: 14px;
            font-weight: 900;
        }

        .newsfrom {
            color: #000302;
            font-size: 24px;
            font-weight: 900;
        }

        .paragraph {
            color: #07c3fc;
            font-size: 18px;
            font-weight: 900;
        }

        #f011 {
            color: #000000;
            font-size: 18px;
            font-weight: 900;
        }
    </style>
</head>
<body>


<!-- 1 -->
<span class="Character1">
    G
</span>

<span class="Character2">
    o
</span>

<span class="Character3">
    o
</span>

<span class="Character4">
    g
</span>

<span class="Character5">
    l
</span>

<span class="Character6">
    e
</span>

<br><br><br><br><br>

<!-- 2 -->
<!-- 标题改成红色，副标题改成橙色字体改成14px  时间改成蓝色 来源改成绿色  段落改成粉色   央视网消息（新闻联播）改成24px 并且改成黑色-->
<!-- 所有的段落字体改成18像素 -->

<strong class="newstitle">【1231231】123123112</strong>
<br><br>
<small class="subtitle"><span>08:13:54</span>&nbsp;&nbsp;<span class="source">来源:</span>&nbsp;<span class="newsfrom">123</span></small> 
<br>
<p class="paragraph">1111111111111111</p>

<p class="paragraph">1111111111111
</p>


</body>
</html>
```

------



### 样式的继承

> **样式继承:并不是所有的样式都会继承的**
>
> ​	有一些样式,父元素(标签)设置该样式以后  子元素(标签)会进行继承 
>
> ​	如果说子元素本身自己设置该样式，那它会先使用自己的样式，如果本身没有就会去继承父元素的样式
>
> ​	**color,font-size这两个属性是会继承给子元素**的
>
> ​	css样式非常多,我们在用的时候 不确定继承还是不继承的前提，边用边看就行。如果继承了 你不希望继承 那就改子元素。



### 样式的先后顺序

> css:层叠样式表
>
> > ​    **后面**的样式会**覆盖****前面**的样式
> >
> > ​    同一个样式属性后面会覆盖前面的样式

------



### 样式的优先级



​    同一个样式**权重不一样（选择器不一样）**它会先使用优先级权重最大的那一个,如果说不同的样式 那么按照**选择器优先级层叠（覆盖）**

​    **权重相同**那么按照**先后顺序重叠（覆盖）**

------



### 部分简单的样式

> **border**：10表示变宽的粗细 solid 实线边款 red边框的颜色

```html
<style>
	.one{
      border: 2px solid black ;
    }
</style>

<h1 class="one">我是一个标题</h1>
```

------



> **背景颜色：background-color**

```css
<style>
	.one{
      background-color:orange;
    }
</style>
```

------



> 有一些元素 如果没有设置宽度它的宽度和高度是auto 自动 父元素多宽 它就有宽

固定宽度: **width** / width: auto;

```css
<style>
	.one{
      width: 300px;
    }
</style>
```

固定高度: **height** / height: auto;

```css
<style>
	.one{
      height: 300px;
    }
</style>
```

最小的宽度: **min-width** 当前元素不能小于300px

```css
<style>
	.one{
      min-width:300px;
    }
</style>
```

最大的宽度: **max-width** 当前元素的宽度不能大于300

```css
<style>
	.one{
      max-width:300px;
    }
</style>
```

最小高度: **min-height** 如果说内容超出了300 自动被内容撑高

```css
<style>
	.one{
      min-height: 300px;
    }
</style>
```

最大高度: **max-height** 如果说内容低于300 内容又多高当前元素就多高,如果说超出当前高度 不会再变高了

```css
<style>
	.one{
      max-height: 300px;
    }
</style>
```

------



### 元素的区分(重点)

> 元素分成以下几种元素
>
> ​	1.**块级元素** 即使做了元素的宽高  元素也会占据一行的。
>
> ​		**e.g. h1-h6  div p ul li ol li**
>
> ​		元素默认占据一行
>
> ​		元素宽高有效
>
> ​	2.**行内元素**(行元素  内联元素) 
>
> ​		**e.g. strong em span a** 
>
> ​		元素不会占据一行
>
> ​		元素宽高是无效的
>
> ​	3.**行内块元素**  
>
> ​		**e.g. img input button**
>
> ​		宽高有效
>
> ​		元素不会占一行

------



### 颜色

> 颜色可以使用单词
>
> > ​     也可以使用rgb颜色 r:red g:green b:blue
> >
> > ​     3个值分别再0-255之间
> >
> > ​     **rgb()**

```css
<style>
	.one{
      background-color:rgb(208, 229, 255);
    }
</style>
```

------



> **rgba**:三原色+透明度  a:透明度
>
> > ​     这个度的值 0-1之间  0全透明  1表示不透名（中间可以用.5来简写）

```css
<style>
	.one{
      background-color: rgba(255, 0, 0, 0.5);
    }
</style>
```

------



> **16进制颜色，**#6位
>
> > ​	如果说前后两位的值相同可以缩写
> >
> > > ​		\#aabbcc  #abc  #dddddd #ddd

```css
<style>
	.one{
      background-color:#f50;
      color: #bdf;
    }
</style>
```

------





## Day10_文本/列表/伪类/元素的转换

### 字体样式

#### 字体的颜色

> 颜色也可以用16进制或者RGB表示

```css
color: orange;
```

------



#### 字体的大小

> chrome浏览器在不设置字体大小的情况默认是16px 
>
> 不同浏览器的默认字体大小有可能是不一样
>
> > ​	在chrome里面字体最小是12px 0就没了

```css
font-size: 30px;
```

------



#### 字体的粗细

>  bold:粗体
>
>  normal:标准的字体 正常的字体

```css
font-weight: bold；
font-weight: normal;
```

------



#### 字体的风格

> italic:斜体
>
> normal:标准的字体 正常的字体

```css
font-style:normal;
```

------



#### 字体族（字体类型）

> 设置字体的时候 可以多设置几个,
>
> > ​	浏览器会一个个字体和当前电脑中的字体匹配,匹配上哪个就用哪个
> >
> > ​	如果不全部匹配不上 就用默认的 默认的微软雅黑

```css
font-family:"KaiTi",'宋体','隶书';
```

------



### 文本样式

> 注：样式继承 多个祖先元素设置同一个样式的时候会先考虑最近的祖先元素

#### 首行缩进

> em：单位 它是一个响应式单位。它是看当前的字体大小是1个em就是多少  
>
> > ​	如果当前没有设置字体大小 它会往上级查找，找到最近
> >
> > ​	有设置字体大小的祖先元素，1个em就等于找到的字体大小,如果说全部的祖先元素都没有设置字体大小，那么1em就等于浏览的默认字体大小

```css
text-indent: 2em;
```

------



#### 文本的装饰

> underline:下划线  
>
> overline:上划线
>
> line-through:删除线
>
> （最常用）none:没有装饰 可以将一些有装饰的内容去掉装饰线

```css
text-decoration:none;
```

------



##### 装饰线的类型 

> wavy：波浪线  
>
> solid:实线  
>
> dashed：虚线  dotted:点

```css
text-decoration-style:dashed; 
```

------



##### 装饰线的位置 

> underline:下划线  
>
> overline：上划线  
>
> line-through:删除线

```css
text-decoration-line:underline;
```

------



##### 装饰线的颜色

```css
text-decoration-color: red; 
```

------



##### 装饰线的简写

> 无先后顺序

```css
text-decoration:underline dotted blue;
```

------



#### 文本的排版

> 它是对齐于当前元素的位置
>
> 它可以排版内部的除了块级元素以外的元素，如果内部是块元素，块元素是无效的。
>
> 但是内部的元素同样会继承这个属性 内部的元素又会对自己内部的元素或者文本进行排版

> ​        left:左对齐
>
> ​        right:右对齐
>
> ​        center:居中对齐
>
> ​        justify:两端对齐

```css
text-align: center;
```

------



#### 文本的转换

> uppercase:将字母转换成大写字母
>
> lowercase:转换成小写的字母
>
> capitalize:首字母大小，它在区分单词时候的是以空格为单位区分

```css
text-transform: capitalize;
```

------



#### 字符之间的间距

> 不管是中文/英文/字母/标点符号/数字

```css
letter-spacing: 50px;
```

------



#### 单词之间的间距

> 以空格为区间

```css
word-spacing:50px;
```



#### 元素文本的处理方式

> pre: 保留换行和缩进
>
> pre-line：保留换行 但是不保留缩进
>
> nowrap: 文本不自动换行

```css
white-space:pre;
```

> ​	当一个容器内文本文字如果说超出了容器宽度 它自动会换行。
>
> ​	但是如果说这个单词很长，它会将这个单词画在一行当中,直到这个单词结束以后再换行。



> **pre可以单独作为一个标签使用？**

```css
  <pre>
      var a = 10;
      function fn (){
        return a+20
      }
      fn()
  </pre>
```

------



### 宽高的问题

> 块级元素再没有设置宽高高的时候,auto
>
> 可以暂时理解位是width相对于父组件100%  宽度是可以设置百分比额
>
> 高度就是由里面内容撑开的
>
> ​	如果内部的元素希望和父元素宽度一样的情况,方案有很多种

```css
.outer{
      width: 600px;
      height: 500px;
      background-color:bisque ;
    }
  
.inner{
  width: 100%;
  background-color: blueviolet;
}
```

------



### 列表的样式

#### 列表前面的符号的样式

> square 实体正方形 
>
> circle 空心圆 
>
> none:将前面的符号去除（最常用）

```css
list-style-type:none;
```

```css
/* 最常用的 去除前面的符号*/
list-style:none;
```

------



#### 列表前面的符号的位置

> 表示前面的符号的位置 
>
> ​     inside:前面符号在li内部
>
> ​     outside：前面符号在li的外部

```css
list-style-position:outside;
```

------



#### 列表前面的符号为图片

> 修改li前面的图标为图片 url表示的是图片的地址

```css
list-style-image:url(./icon.png);
```

------



### 超链接伪类

#### 伪类选择器

##### 没有访问过的超链接样式

> 格式：link

```css
a:link{
      color: rgb(212, 56, 56);
}
```

------



##### 当前浏览器访问过的超链接样式

> 格式：visited

```css
a:visited{
  color: rgb(171, 147, 115);
}
```

------



##### 鼠标移入当前超链接上以后的样式的

> 格式：hover

```css
a:hover{
      color: red;
      font-size: 40px;
      font-weight: bold;
}
```

------



##### 当鼠标点击超链接的时候触发的样式

> 格式：active

```css
a:active{
      color: pink;
      font-size: 40px;
} 
```

------



##### 记忆

> LVHA，记住HA，这两个伪类可以在任何标签上使用。

```css
.box:hover{
  background-color: red;
  text-align: center;
  color: #fff;
}

.box:active{
  background-color: greenyellow;
  text-align: center;
}
```

------



### 鼠标的样式

> **可以去这个网址查询前端的很多知识**
>
> > ​	**https://developer.mozilla.org**



> cursor：鼠标展示的效果，**注意这个一定要加wait**
>
> > ​	pointer:手
> >
> > ​	url(./icon.png),wait。自定义鼠标的图标

```css
cursor: url(./icon.png),wait;
```

------



### 元素的转换

> 使用display属性进行block，inline，inline-block的转换

```css
display: inline-block;
display: block;
display: inline;
```

------



### 超链接变按钮

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    a{
      width: 120px;
      height: 30px;
      background-color: #1b1b1b;
      color: #fff;
      display: block;
      font-size: 14px;
      text-align: center;
      /* 当前元素多高 这里设置多少内部就会垂直居中 下周会详细讲 */
      line-height:30px;
      /* 圆角 */
      border-radius:6px;
      cursor: pointer;
      text-decoration: none;
    }
    a:hover{
      background-color: #696969;
    }
  </style>
</head>
<body>
  

  <a href="">Get MDN Plus</a>

</body>
</html>
```

------



## Day11_文字/盒子模型/选择器

### 文字

#### 文字的基线问题

> **在一行当中文字默认是以基线对齐的,基线就是x的底部**。



> **vertical-align**：指定行内元素或者行内块元素垂直对齐方式。
>
> ​	***记住，这里是元素，并且块元素无法对齐。**
>
> > ​	baseline:沿着基线（x底部）对齐
> >
> > ​	bottom:沿着底部对齐
> >
> > ​	top:沿着顶部对齐
> >
> > ​	middle:当前元素的中部于字母x的中部对齐
> >
> > ​	**图片和文字之间布局关系可以用用这个属性来完成。**

```css
vertical-align: middle;
```

------



#### 文字的行高问题

> 行高: 一行文字的高度
>
> > ​      行于行之间是链接的。文字查不到就在行高的中间
> >
> > ​      值可以一个固定像素
> >
> > ​      可以写倍数 这个倍数是当前文字大小的倍数

```css
line-height: 1.5;
line-height: 15px;
```

------



> **元素有多高 行高设置多少文字就会垂直居中**

```css
div{
      width: 200px;
      height: 200px;
      background-color: teal;
      line-height: 200px;
      font-size: 24px;
      font-family: "楷体";
      line-height: 200px;
      font-weight: bold;
}
```

------



> **字体的简写**
>
> > ​	**一定要按照一定的顺序，不能打乱顺序**
> >
> > ​	**字体粗细（空格）字体大小/字体行高（空格）字体族**

```css
font:bold 24px/200px "楷体";
```

------



### 盒子模型

>    **所有的元素（标签）都是盒子 块盒 行盒**
>
>    **一个标准的盒模型 = content + margin + padding + border**



#### 边框 border

> top:上边 right:右边 bottom:下边  left:左边
>
> > ​    border-方位-style: 指定方位的边框风格 
> >
> > > ​		solid: 实线 / dashed: 虚线 / dotted: 小圆点 / none: 没有
> >
> > ​    border-方位-width: 指定方位的边框粗细
> >
> > ​    border-方位-color: 指定方位的边框颜色

```css
border-top-style:solid;
border-top-width:10px;
border-top-color:red;
border-right-style: dashed;
border-right-width: 10px;
border-right-color: blue;
```

------



> **border-方位: 指定一个方向边框的风格粗细颜色的简写形式, 没有顺序要求。**

```css
border-left:10px solid blue;
border-top:10px dashed pink;
```

------



> **同时设置四个方位边框样式 简写形式是没有顺序的要求。**

```css
border: 10px solid blue;
```

------



#### 外边距 margin

> **当前盒子外部的区域,离相邻元素之间的距离。**



> 单独设置某一个方向的外边距

```css
margin-right: 50px; 
margin-left: 50px;
margin-bottom: 50px;
margin-top: 50px;
margin-right: 50px;
```

------



> 同时设置四方向的外边距

```css
margin: 50px;
```

------



> 同时设置三方向的外边距

```css
/* 上10/左右20/下30 */
margin: 10px 20px 30px;
```

------



> 同时设置两方向的外边距

```css
/* 上下位10  左右20 */
margin: 10px 20px;
```

> ​	使用auto，自动分配左右两边外边距。然后让自己居中于父元素中间。
>
> > ​	**并且只对块元素有效**

```css
margin:50px auto;
```

------



#### 外边距的问题

> 外边距塌陷问题,给子元素设置上下外边距的时候, 外边距会自动传递给父元素. 
>
> > ​	**上下外边距会重叠 ，但是左右外边距不会重叠。**



> ​	1. **方案高度塌陷问题解决，给父元素加个边框****

```css
border: 1px solid yellow;
```

>  2. **方案高度塌陷问题解决， BFC**
>
>     上下外边距会重叠，如果说不希望上下外边距重叠，再某一个元素外面套一个盒子,然后让这个盒模型开启BFC(overflow: hidden;)

```css
overflow: hidden;
```

------



##### 再次总结三种元素的不同

> ​	**块元素:宽高有效，独自占一行，上下外边距有效。**
>
> ​	**行内元素:宽高无效，不会独自占一行，上下外边距无效。**
>
> ​	**行内块:宽高有效，不会独自占一行，上下外边距有效。**

------



#### 内边距 padding

> 当前的元素的边框离内容之间的距离
>
> > ​	书写方式同外边距

------

```css
padding-left:30px;
padding-top:30px;
padding-right: 30px;
padding-bottom:30px;
```

------



#### 宽度的问题

> **边框是会影响整个盒子可见宽高**
>
> **内边距也会影响整个盒子的可见宽高**
>
> **外边距不会影响可见宽高，但是再当前这一层，所占位置会被影响。**



> **如果说元素没有设置宽度。做内边距的时候，左右内边距是不会影响整体宽度。浏览器会自动调整。**

```css
.inner{
  /* width: 100%; */
  height: 100px;
  background-color:orange;
  padding: 20px;
}
```

------



#### 元素自带的内外边距

> 由于90年代html发展的原因，很多元素都会带有内外边距。
>
> > ​	所以需要一次性清除所有的元素的内外边距。

```css
*{
  margin: 0;
  padding: 0;
}
```

------



### 选择器拓展

> css中选择器有许多种，以后还会扩充。



#### 通配选择器

> 选择所有的元素 包括html body这些

```css
*{
	color: red;
} 
```

------



#### 并集选择器

> 选择多个指定的所有元素。
>
> > ​	**使用,隔开每个元素**

```css
.one,.two,strong,span,div{
        background-color: red;
}
```

------



#### 交集选择器

> 选中 p标签并且p标签中带有指定类名或者id名，
>
> > **使用.连接每个元素**
> >
> > **注意，交集选择器中标签选择器只能有一个。**

```css
p.one{
	background-color: red;
} 
```

------



#### 子选择器

> 它选中的是指定元素的孩子元素，可以有多个元素。
>
> > ​	**使用a > b**。选择器孩子的b。

```css
.box > div > span{
	color: red;
} 
```

------



#### 后代选择器

> 选择元素不管是儿子还是孙子的所有元素（所有的后代）
>
> > ​	**使用空格隔开每个元素。**

```css
.box div span{
      color: red;
} 
```

------



#### 选择器的权重

> 要看怎么去选择它的。
>
> > ​	选择到这个元素的时候 **进行单独提取选择器的值计算**
> >
> > ​	**注意，如果是并集选择器，还是使用叠加的原理。**
> >
> > ​	**注意，通配选择器没有权重。**



> **选择器的优先级**
>
> ​    **!important(10000) > 行内样式(1000) > id选择(100) > 类选择器(10) > 标签选择器(1) > 通配选择器(0)**



> 这里11 > 10,所以会以span.abc的结果为准。

```
/* 1 + 10 */
span.abc{
	color: blue;
} 

/* 10 */
.abc{
	color: red;
} 
```

------

