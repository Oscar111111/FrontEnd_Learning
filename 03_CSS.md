#  CSS

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
>
> CSS中选择器有许多种，以后还会扩充。
>
> https://caniuse.com/ 
>
> ​	查看一些东西哪些浏览器支持 哪些浏览器不支持



#### 选择器 Selectors

##### 通配选择器

**Universal selectors**

> 选择所有的元素 包括html body这些

```css
*{
	color: red;
} 
```

------



##### 标签选择器

**Type selectors**

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



##### id选择器

**ID selectors**

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



##### 类选择器

**Class selectors**

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



##### 属性选择器（重）

**Attribute selectors**

> **[属性名] ，只要元素有该属性就能选中**



> **[class]**
>
> > ​	选择属性名为class的全部元素

```css
[class]{
	color: blue;
} 
```

------



> **a[title]**
>
> > ​	这里结合交集选择器，选择是a标签，并且属性名是title的元素。

```css
a[title]{
	color: red;
}
```

------



> **[属性 = 属性值]** 
>
> > ​	有该属性，并且有对应的值

```css
a[title='abc-cba']{
	background-color: yellow;
} 
```

------



> **[属性^ = 属性值]** 
>
> > ​	有该属性，并且属性值是以什么开头的

```css
a[title^='abc']{
	background-color: pink;
} 
```

------



> **[属性$ = 属性值]** 
>
> > ​	有该属性，并且属性值是以什么结尾的

```css
a[title$='cba']{
	background-color: yellow;
} 
```

------



> **[属性* = 属性值]** 
>
> > ​	有该属性，并且包含什么属性值

```css
a[title*='oo']{
	background-color: pink;
} 
```

------



#### 组合器 Combinators

##### 并集选择器

**Selector list**

> 选择多个指定的所有元素。
>
> > ​	**使用,隔开每个元素**

```css
.one,.two,strong,span,div{
        background-color: red;
}
```

------



##### 交集选择器

> 选中 p标签并且p标签中带有指定类名或者id名或者属性名等
>
> > **注意，交集选择器中标签选择器只能有一个。**
> >
> > 其实交集就是把两个元素合起来，**不带空格！**

```css
p.one{
	background-color: red;
} 
p#one{
	background-color: red;
} 
p[one]{
	background-color: red;
} 
```

------



##### 紧邻兄弟组合器

**Adjacent sibling combinator**

> 用于找到此元素同级的其他元素

​	

> ​	**.two + li**
>
> > ​	找指定元素的后一个兄弟元素, 是否是指定的元素 是就选中，不是就不选中

```css
.two + li{
	background-color: yellow;
} 
```

------



##### 一般兄弟组合器

**General sibling combinator**

> ​	**.two ~ li**
>
> > ​		找指定元素的后面所有兄弟li,记住必须是同级。

```css
.two ~ li{
  background-color: yellow;
}
```

------



##### 子选择器

**Child combinator**

> 它选中的是指定元素的孩子元素，可以有多个元素。
>
> > ​	**使用a > b**。选择器孩子的b。

```css
.box > div > span{
	color: red;
} 
```

------



##### 后代组合器

**Descendant combinator**

> 选择元素不管是儿子还是孙子的所有元素（所有的后代）
>
> > ​	**使用空格隔开每个元素。**

```css
.box div span{
      color: red;
} 
```

------



#### 伪选择器

> ​	伪选择器分为伪类选择器（**Pseudo-classes**，前面一个冒号）和伪元素选择器（**Pseudo-elements**，前面两个冒号）
>
> ​	为了方便记忆，以下都写为**伪选择器**



##### 根

> ​	:root，等价于 html

```css
:root{
  border: 2px solid red;
}
```

------



##### 超链接

###### :link

> 没有访问过的超链接样式



> 格式：link

```css
a:link{
      color: rgb(212, 56, 56);
}
```

------



###### :visited

> 当前浏览器访问过的超链接样式



> 格式：visited

```css
a:visited{
  color: rgb(171, 147, 115);
}
```

------



###### :hover

> 鼠标移入当前超链接或元素上以后的样式的



> 格式：hover

```css
a:hover{
      color: red;
      font-size: 40px;
      font-weight: bold;
}
```



###### 让其他元素也能显示hover的效果

> ​	我们可以对某元素设置hover，从而让其他元素也能带有hover的效果。
>
> > ​	**注意!:选择器必须要选对！**

 

###### **应用场景1**

> ​		**实现鼠标经过显示和隐藏列表**

 

> 将子列表设置为display: none;隐藏，然后将父列表设置为hover属性，并且同时设置display: block;属性。这样鼠标移到父元素上，子元素就能显示出来。

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .menu>li {
      border: 2px solid blue;
    }

    .pList {
      display: none;
    }

    .ppList {
      display: none;
    }

    .menu li:hover .pList {
      display: block;
      background-color: yellow;
    }
  </style>
</head>

<body>

  <ul class="menu">
    <li>
      <ul class="pList">
        <li>小米</li>
        <li>华为</li>
      </ul>
      <a href="">手机</a>
    </li>
    <li>
      <ul class="pList">
        <li>联想</li>
        <li>三星</li>
      </ul>
      <a href="">电脑</a>
    </li>
    <li>
      <ul class="pList">
        <li>小米</li>
        <li>华为</li>
      </ul>
      <a href="">手机</a>
    </li>
  </ul>



</body>

</html>
```

------



###### :active

> 当鼠标点击超链接或元素的时候触发的样式



> 格式：active

```css
a:active{
      color: pink;
      font-size: 40px;
} 
```

------



###### **记忆**

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





##### nth（重）

###### **child**系列

> **:first-child**
>
> 先查找指定选择的父元素,判断这个这个父元素中**第一个元素**是否是该元素，是就选中，不是就不选中

```css
p:first-child {
	background-color: red;
} 
```

------



> **:last-child**
>
> > 先查找指定选择的父元素,判断这个这个父元素中**最后一个元素**是否是该元素，是就选中，不是就不选中

```css
p:last-child {
	background-color: blue;
} 
```



> **:nth-child()**
>
> > ​	odd:奇数,其实就是2n+1
> >
> > ​	even:偶数，其实就是2n
> >
> > ​	选择指定后几位的时候 an+b
> >
> > ​	选择前几位是 -an+b

```css
p:nth-child(-2n+5) {
      background-color: pink;
}

p:nth-child(odd) {
	background-color: pink;
}
```

------



###### oftype系列

> **:first-of-type**
>
> 先查找指定选择器的父元素,直接找该父亲中指定的**第一个**元素给他选中

```css
p:first-of-type {
	background-color: red;
} 
```

------



> **:last-of-type**
>
> > 先查找指定选择器的父元素,直接找该父亲中指定的**最后一个**元素给他选中

```css
p:last-of-type {
	background-color: blue;
} 
```



> **:nth-of-type()**
>
> > 写法和nth-child（）是一样，只是查找的规则不同。
> >
> > 找到父元素中第几个这个元素，然后选中他
>
> > ​	odd:奇数,其实就是2n+1
> >
> > ​	even:偶数，其实就是2n
> >
> > ​	选择指定后几位的时候 an+b
> >
> > ​	选择前几位是 -an+b

```css
p:nth-of-type(-2n+5) {
      background-color: pink;
}

p:nth-of-type(odd) {
	background-color: pink;
}
```

------



##### 表单

###### :focus （记）

> ​	表示对表单获取焦点的时候做样式修改

```css
:focus{
      background-color:red;
} 
```

------



###### :disabled

> 表示对禁用的表单做样式修改

```css
:disabled{
      background-color: pink;
} 
```

------



###### :enabled

> 表示对可用的表单做样式修改

```css
:enabled{
} 
```

------



###### :read-only

> 表示对只读的表单做样式修改

```css
input:read-only{
      background-color: blue;
}
```

------



###### :required

> 表示对必须要填的表单做样式修改

```css
input:required{
      background-color: yellow;
}
```

------



###### :checked 

> 表示对radio和checked选中状态的时候，做样式修改
>
> > ​		修改不了背景颜色，暂时只能改大小
> >
> > ​		只要用户选中了，就会呈现这个效果

```css
input:checked{
      width: 50px;
      height: 22px;
      background-color: red;
}
```

------



###### ::placeholder （记）

> 修改的样式是placeholder的值

```css
input::placeholder{
      color: pink;
      font-size: 50px;
}
```

------



##### 目标（锚点）

###### :target 描点

> 与锚点配合使用
>
> 当地址栏中锚点（hash）值变了以后 它会选择对应的id

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    ul{
      position: fixed;
      right: 100px;
      top: 0;
    }
    /* 当地址栏中锚点（hash）值变了以后 它会选择对应的id */
    h2:target{
      background-color: red;
    }
  </style>
</head>

<body>
  <ul>
    <li><a href="#one">第一章</a></li>
    <li><a href="#two">第二章</a></li>
    <li><a href="#three">第三章</a></li>
  </ul>




  <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
  <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
  <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
  <!-- 
    任何一个标签都有一个属性叫做id id的值
  -->
  <h2 id="one">这里是第一章内容的区域</h2>
  <p>
    我是第一张内容我是第一张内容我是第一张内容我是第一张内容我是第一张内容我是第一张内容我是第一张内容我是第一张内容我是第一张内容我是第一张内容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第一张内容我是第一张内容我是第一张内容我是第一张内容我是第一张内容我是第一张内容我是第一张内容
  </p>
  <p>
    我是第一张内容我是第一张内容我是第一张内容我是第一张内容我是第一张内容我是第一张内容我是第一张内容我是第一张内容我是第一张内容我是第一张内容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第容我是第一张内容我是第一张内容我是第一张内容我是第一张内容我是第一张内容我是第一张内容我是第一张内容我是第一张内容
  </p>
  <h2 id="two">这里是第二章内容的区域</h2>
  <p>
    我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容
  </p>
  <p>
    我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容 我是第二章内容
  </p>
  <h2 id="three">这里是第三章内容的区域</h2>
  <p>
    我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容
  </p>
  <p>
    我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容
  </p>
  <p>
    我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容
  </p>
  <p>
    我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容我是第三章内容
  </p>
</body>

</html>
```

------







##### ::after 和 ::before （前后加内容）

> **格式：**类似与行内元素，这个伪元素内可以直接去写样式
>
> >    ::after  指定选择器里面的最后面
> >
> >    ::before 指定选择器里面的最前面

```css
p::before{
      /* 这个属性：添加的内容 它只能配合::after ::before使用，内容可为空 */
      content:"哈哈";
      width: 200px;
      height: 200px;
      color: red;
      background-color: yellow;
      display: block;
}

<p>我是一个段落</p>
```

------



##### 文本选择器

###### ::selection 文本

> ​	选择指定元素（文本）中内容后的样式
>
> ​	属性很新，可能很多浏览器不支持

```css
p::selection{
      background-color: red;
      color: pink;
}
```

------



###### ::first-letter 文本

> ​	选择文本中的第一行字符
>

```css
p::first-letter{
      background-color: red;
} 
```

------



###### ::first-line 文本

> ​	选择文本中的第一个字符
>

```css
p::first-line{
      background-color: aqua;
} 
```

------



###### :empty 文本

> 选择空内容的元素，比如空文本框等，里面必须什么东西都没有的

```css
li:empty{
      background-color: yellow;
}
```

------





### 选择器的权重

> 要看怎么去选择它的。
>
> > ​	选择到这个元素的时候 **进行单独提取选择器的值计算**
> >
> > ​	**注意，如果是并集选择器，还是使用叠加的原理。**
> >
> > ​	**注意，通配选择器没有权重。**



> **选择器的优先级**
>
> ​    **!important(10000) > 行内样式(1000) > id选择(100) > 类选择器，伪选择器，属性选择器 (10) > 标签选择器(1) > 通配选择器(0)**



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

​	后续会详细讲优先级。

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
> ​		**e.g. h1-h6，div，p，ul li，ol li**
>
> ​		元素默认占据一行
>
> ​		元素宽高有效
>
> ​	2.**行内元素**(行元素  内联元素) 
>
> ​		**e.g. strong，em，span，a** 
>
> ​		元素不会占据一行
>
> ​		元素宽高是无效的
>
> ​	3.**行内块元素**  
>
> ​		**e.g. img，input，button**
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



### 透明度

> 我们可以对颜色和图片设置透明度。
>
> > ​	例如上文的rgba，a的值0-1.或者直接将背景颜色的值设为transparent，表示透明。还可以使用opacity设置。

​	

> ​	**background-color: transparent;** 
>
> ​	**background-color: rgba(0, 0, 0, 0.3);**
>
> ​	**opacity:.4;** 
>
> > ​		**0-1之间的透明度  1不透明 0完全透明  值越小越透明**

 	

#### **rgba和opacity的区别**

> ​	**1.rgba只针对于颜色， opacity可以透明元素**
>
> ​	**2.有子元素的情况下，rgba只能透明当前元素本身，opacity 不仅透明自己还透明子元素**
>
> ​	**3.rgba只能针对颜色进行透明，opacity可以对任何东西都透明**

------





## Day10_文本，列表，伪类，元素的转换

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



#### 单行文本溢出处理

> 我们可以用css修饰，将单行文本的溢出内容隐藏。但是多行文本的隐藏比较复杂，后续可能学习到？

​	**步骤**

> ​		1.文字不要换行 
>
> 			white-space:nowrap;
>
> ​		2.溢出隐藏 
>
> 			overflow: hidden;
>
> ​		3.溢出内容出现省略号
>
> ```
> 	 text-overflow: ellipsis;
> ```

------

**有时候溢出隐藏没有省略号的点是怎么回事？**

> **因为 text-overflow: ellipsis; 并不会强制“溢出”事件的发生，因此为了能让文本能够溢出容器，就需要给 text-overflow: ellipsis; 配上两个个额外的属性：overflow 和&nbsp;white-space。**

```css
	p{
      position: absolute;
      /* bottom: 0; */
      width: 100%;
      background-color: yellow;
      
      white-space:nowrap;
      overflow: hidden;
      text-overflow: ellipsis;
      
    }
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

> 1. 在开发中，无论我们敲多少空格和回车，显示在页面上的都会合并成一个。
> 2. 我们的文字在超过一行的情况下，就会自动换行。

> **white-space 属性**处理元素内的空白
>
> > ​	空白包括：**Space(空格)、Enter(回车)、Tab(制表符)**



> normal(默认)：所有连续的空格、回车、制表符都合并成一个空格，文本自动换行
>
> nowrap: 所有连续的空格、回车、制表符都合并成一个空格，文本不换行
>
> pre: 所有东西原样输出，文本不换行
>
> pre-wrap：所有东西原样输出，文本换行
>
> pre-line：所有连续的空格、制表符合并成一个空格，回车不变，文本换行

```css
white-space:pre;
```

> ​	当一个容器内文本文字如果说超出了容器宽度 它自动会换行。
>
> ​	但是如果说这个单词很长，它会将这个单词画在一行当中,直到这个单词结束以后再换行。



> **white-space:pre; 等价于<pre></pre>**

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
> **none:将前面的符号去除（最常用）**
>
> **将ul后面的空白去掉，可以将ul的外边距，内边距设置为0解决。**

```css
list-style-type:none;
```

```css
/* 最常用的 去除前面的符号*/
list-style:none;
```

```css
  ul{
    padding:0;
    margin:0;
  }
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



## Day11_文字，盒子模型

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



> **元素有多高 行高设置多少文字就会上下垂直居中**
>
> > ​	**记住，只是上下，左右还不是居中！！**！

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
> >
> > > ​		**可以用transparent表示透明**

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
>
> > ​	**谷歌浏览器默认存在8px 上下左右的外边距**



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

------





#### 外边距的问题

##### **块元素居中**

> 使用auto，自动分配左右两边外边距。然后让自己居中于父元素中间。
>
> > **并且只对块元素有效**
> >
> > > **块元素无法使用text-align: center;**

```css
/* 单左右居中 */
margin:auto;
/* 设置上下居中 */
margin:50px auto;
```



##### 外边距塌陷（重叠）问题

> **margin collapsing**
>
> 给子元素设置上下外边距的时候, 外边距会自动传递给父元素. 
>
> 两个相邻的的元素之间上下外边距会重叠
>
> > ​	**上下外边距会重叠 ，但是左右外边距不会重叠。**



> **解决方法**
>
> > **1. 给父元素加个边框**

```css
border: 1px solid yellow;
```

>  > **2. 使用BFC，后续详细讲**
>
>  > ​	如果说不希望上下外边距重叠，在某一个元素外面套一个盒子,然后让外面这个盒模型开启BFC (overflow: hidden;)

```css
overflow: hidden;
```

> ​	**3. 将父元素变为行内块元素**
>
> > ​			**其实也是开启bfc一种方式**

------



##### inline元素无法设置上下margin

> **行内元素不能设置上下margin，但是padding和border可以设置。**
>
> > ​	原因可能是行内元素的高低是按照文字的高低自动分配的。

------



##### **再次总结三种元素的不同**

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



#### 盒模型的宽度的问题

> **border会影响整个盒子可见宽高**
>
> **padding也会影响整个盒子的可见宽高****
>
> > ​	**可以改变content的大小，颜色随内容**
>
> **margin不会影响可见宽高**，但是再当前这一层，所占位置会被影响。
>
> > ​	**可以改变此容器跟相邻容器的距离**



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
> >
> > > ​	**比如：h1-6，p，ul**

##### 方案一：清除所有元素的默认内外边距

```css
*{
  margin: 0;
  padding: 0;
}
```



##### 方案二：引入别人写好的样式

> ​	好处，不只是可以内外边距设置好了，文字大小，基线，行高等。都可以自定义设置。

**GitHub地址：**

​	reset和normalize，两个github版本



------



## Day12_去除空格/缝隙，浮动



### 去除行内元素的空格

> **由于书写习惯，行内元素与其他元素之间会存在一个空格**

> **解决方法**：
>
> > ​	空格就是一个字符，只需要将这个空格字符选中以后 让他字体大小设置为0

```css
*{
      font-size: 0;
}
html{
      font-size: 0;
}
body{
      font-size: 0;
}
```

然后可以把一些常用的字体给它统一加上一个字体大小

```css
div,span,a,ul,li,p,h1,h2,h3,strong,em,i,input,button{
	font-size: 16px;
}
```

------



### 去除元素的缝隙

> **元素（行内块或者图片等）与父元素是会存在缝隙的。**

**解决方法**：

 1. 使用文字的底部对齐，或者其他对齐方式

    ```css
    vertical-align:bottom;
    ```

 2. 将子元素变成块元素

    ```css
    display: block;
    ```

3. 将子元素的高度设置与父元素一样

   ```css
   .outer{
    
     height: 250px;
   }
     
   .inner{
     height: 100%;
   }
   ```

------







### 浮动

> 指定一个元素应沿其容器的左侧或右侧放置，**允许文本和内联元素环绕它**。该元素从网页的正常流动（文档流）中移除，但是仍然保持部分的流动性**（与[绝对定位](https://developer.mozilla.org/zh-CN/docs/Web/CSS/position#absolute_positioning)相反）**。



**格式**

> **浮动无法被子元素继承 ！**
>
> float:
>
> > ​	left:左浮动
> >
> > ​	right:有浮动

```css
.box2 {
      width: 120px;
      height: 120px;
      background-color: blue;
      float: left;
      /* float: left; */
}
```

------



#### 浮动的特点

> **1.当元素浮动以后会脱离文档流**
>
> **2.元素会往左上角或者右上角漂移，直到碰到父元素的边界停止,或者兄弟元素停止**
>
> **3.当一个元素浮动以后，那么就没有块级元素和行内元素区分了。	**
>
> ​		**称作浮动元素，类似行内块元素特性，但是不是行内块元素。**
>
> **4.相邻的元素同时做了一个方向浮动，紧紧的挨在一起**

------



#### 浮动环绕效果

> 当一个元素浮动以后，它后面的元素内部如果是文字，这个元素会跑到它后面。
>
> > ​	**但是它内部的文字是不会跑到它后面的**
> >
> > ​	**这些文字会环绕着这个浮动元素**

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    * {
      margin: 0;
    }

    /* 
      当一个元素浮动以后，它后面的元素内部如果是文字，这个元素会跑到它后面，但是它内部的文字是不会跑到它后面的
      这些文字会环绕着这个浮动元素
    */
    div {
      width: 100px;
      height: 100px;
      float: left;
      background-color: rgba(0, 0, 0, .4);
    }

    p {
      background-color: yellow;
    }

    strong {
      background-color: red;
      font-size: 24px;
    }
  </style>
</head>

<body>

  <div></div>
  <p>
    <strong>备注</strong>： 如果要在 JavaScript 中把 float 属性当作 HTMLElement.style 对象的一个成员来操作，那么在旧版本的浏览器中，你必须拼写成 cssFloat。另外还要注意到在
    Internet Explorer 8 和更老的 IE 当中，要使用 styleFloat 属性。这是 DOM 驼峰命名和 CSS 所用的连字符分隔命名法对应关系中的一个特例（这是因为在 JavaScript
    中“float”是一个保留字，因为同样的原因，“class”被改成了“className” 、<label> 的“for”被改成了“htmlFor”）。
  </p>


</body>

</html>
```

------



#### 浮动对齐方式

> **浮动元素两个紧挨着的元素会以顶部来对齐**
>
> > ​	**并且注意，如果两个元素内部有文字，文字就不会以默认的基线对齐的方式对齐了。**

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
   
    .box{
      background-color: #ddd;
    }
    .box1,.box2{
      /* 浮动元素两个紧挨着的元素会以顶部来对齐 */
      /* display: inline-block; */
      float: left;
    }

    .box1 {
      width: 100px;
      height: 100px;
      background-color: aqua;
    }

    .box2 {
      width: 100px;
      height: 120px;
      background-color: pink;
      font-size: 90px;
    }
  </style>
</head>

<body>

  <div class="box">
    <div class="box1">gx哈哈</div>
    <div class="box2">gxaha</div>
  </div>

</body>

</html>
```

------



#### 清除浮动

> **可以清除浮动对某一元素产生的影响。**

> ​	清除左/右/全部浮动对当前元素产生的影响。
>
> > ​		**对行内元素清除高度塌陷无效**
> >
> > > ​		left:清除左浮动产生的影响
> > >
> > > ​		right:清除有浮动对我产生的影响
> > >
> > > ​		both:清除两者浮动对我产生的影响

```css
clear:right;
```

------



#### 浮动高度塌陷问题

> **float collapsing**
>
> 在文档流中，父元素的高度默认是被子元素撑开的，也就是子元素多高，父元素就多高。但是当为子元素设置浮动以后，子元素会完全脱离文档流，此时将会导致子元素无法撑起父元素的高度，导致父元素的**高度塌陷**。
>
> 由于父元素的高度塌陷了，则父元素下的所有元素都会向上移动，这样将会导致页面布局混乱。



**解决方法：**

> 1. 给高度塌陷的元素加一个高度。
>
> > ​		缺点：有时候不能确定内部元素右多高。

```css
height:100px;
```

> 2. 给当前元素开启bfc(以后再说) 
>
> > ​		缺点:溢出部分会被隐藏掉

```css
overflow: hidden;
```

> ​	3.利用clear属性，用来清除其他浮动元素对当前元素的影响
>
> > ​		缺点：页面中添加多余的结构，导致浏览器性能降低。并且后续可能写样式会对这个标签造成影响。

```css
clear: left;
```

> ​	4. 整体思路和方案三一致，通过after伪类向元素的最后添加一个空白的块元素，然后对其清除浮动

```css
.outer::after{
      content: '';
      width: 50px;
      height: 50px;
      background-color: yellow;
      display: block;
      clear: both;
}
```

------



## Day13_溢出处理，定位，怪异模式，圆角

### 溢出处理

> **溢出是在盒子无法容纳下太多的内容的时候发生的**。

> ​	**使用： overflow属性做溢出处理**

> ​		**overflow：溢出处理**
>
> ​		**overflow-x：做X轴处理，Y轴同理**
>
> > ​			**visible:默认的**
> >
> > ​			**hidden：溢出部分隐藏**
> >
> > ​			**scroll：溢出部分滚动查看**
> >
> > ​			**auto：溢出自动 超出就出现滚动条  不超出就不出现滚动条**

```css
overflow: visible;
overflow-x: visible;
```

------



### 定位

> 定位允许你从正常的文档流布局中取出元素，并使它们具有不同的行为
>
> > ​	例如放在另一个元素的上面，或者始终保持在浏览器视窗内的同一位置。



> ​	可以将网页中的元素根据不同的定位属性放到你想要的的地方去
>
> ​	**定位无法被子元素继承！**

> ​		position:
>
> > ​			static:静态定位，占据正常文档流
> >
> > ​			relative:相对定位，占据正常文档流
> >
> > ​			absolute:绝对定位，脱离文档流
> >
> > ​			fixed:固定定位，脱离文档流
> >
> > ​			sticky:粘性定位，占据正常文档流
> >
> > ​	可以配合以下4个属性使用：
> >
> > ​			left
> >
> > ​			right
> >
> > ​			top
> >
> > ​			bottom
> >
> > ​	*注意：
> >
> > ​	任何定位的时候同一个方向的两个值不要同时使用
> >
> > ​		(正常的情况下left和right不要一起使用  top和bottom不要一起使用)
> >
> > ​     一些特殊情况 必须同时使用。比如后续的**定位的特殊使用**。

------



#### 静态定位

> **将当前的元素开启了静态定位,没有任何效果 ，开和不开没有任何区别 **
>
> **可能会配js使用**

```css
position: static;
top: 10px;
```

------



#### 相对定位

> 相对于**元素本身**的位置来进行移动的 



**特点：**

> 1.根据自己原本的位置来进行定位（相对）
>
> 2.不会脱离文档流的

```css
position: relative;
    /* 这里只会生效left，第一个 */
    left: 50px;
    right: 50px;
```

------



#### 绝对定位

**特点：**

> ​     1.当元素开启绝对定位以后他会脱离文档流
>
> ​     2.绝对定位在定位时候，它会先**找最近的祖先元素看是否开启了定位****(除了static以外)**
>
> ​	如果开启了就以最近的那个祖先为基准，一直往上找所有祖先都没开，它就以浏览器的窗口为基准
>
> ​     3.当元素开启绝对定位以后，元素就不在有行内和块级区分了，因为脱离文档流，它叫定位元素

```css
position: absolute;
      right: 10px;
      /* left: 100px;
      bottom: 10px; */
```



**绝对定位高度塌陷**

> 由于BFC内部的特点（后续说明），在计算BFC的高度时候不会计算内部的绝对高度和固定高度。因为两者完全脱离了文档流。所以会导致高度塌陷。



​	**特点：**

> ​		绝对定位的高度塌陷问题 **bfc是解决不了的**, **只能给个固定高度**
>
>  		如果在**不确定内部高度**是多少的时候，以后**用js操作**

------



#### 固定定位

**特点：**

> ​     1.当元素开启固定定位以后会脱离文档流
>
> ​     2.固定位它是**以浏览器窗口为基准**,祖先素即使开启了定位也没用
>
> ​     3.当元素开启固定定位以后，元素就不在有行内和块级区分了，因为脱离文档流，它叫定位元素

```css
position: absolute;
      right: 10px;
      bottom: 10px;
```



**固定定位高度塌陷**

> 由于BFC内部的特点（后续说明），在计算BFC的高度时候不会计算内部的绝对高度和固定高度。因为两者完全脱离了文档流。所以会导致高度塌陷。



​	**特点：**

> ​		固定定位的高度塌陷问题 **bfc是解决不了的**, **只能给个固定高度**
>
>  		如果在**不确定内部高度**是多少的时候，以后**用js操作**

------



#### 粘性定位

**特点**：

> ​	1. 需要前置的溢出处理知识。
>
> ​	2. 开启粘性定位 再一些**低版本的浏览器**它是无效
>
> ​	3. 不会脱离文档流
>
> ​	4. **以最近的滚动祖先位基准**
>
>  5. 当父元素（可见的大小）超出了可视区域 粘性定位就失效了
>
>     ​	**（重点！：跟内外边距还有边框都没关系）**

```css
 position: sticky;
      top: 10px;
      left: 10px;
```

------



#### 定位的特殊使用

##### 场景1：实现将父元素中的元素居于父元素中间

**文字居中：**

> ​	如果元素内部的文字，想居于元素中间，可以使用（具体可见文字的行高部分）
>
> > ​		text-align: center; 达到文字左右居中
> >
> > ​		设置line-height 的值等于元素的高度，这里无法设置百分比。
> >
> > > ​			**注意！：文字只有一行才能这样子做。**

------



**img图片居中**

**水平居中**

> 方法1：img为内联元素，将img设置为block块元素，并设定其宽度和高度，然后margin：0 auto
>
> 方法2：直接在img所在的父元素中设置text-align：center

**垂直居中**

> 方法1：在img标签前增加一个span元素，设置其为inline-block，高度和其父元素一致100%，设置vertical-align：middle，同时再设置img元素属性vertical-align：middle
>
> 方法2：图片能写到背景的话尽量写到背景里面，位置属性更容易控制一些。也能实现同样的效果。

------



**方案1**

> > ​	将子元素变为块元素，使用 margin: 100px  auto ;属性解决。
> >
> > ​		但是！：会触发外边距塌陷问题，所以暂时解决方法见外边距塌陷问题部分。
> >
> > ​		上下外边距计算为（父元素高度-子元素高度）/ 2.

------



**方案2**

> ​	先设置绝对定位或者固定定位到当前父元素（父元素也要开启定位）的一半位置 
>
> ​	然后使用margin自己回去自己本身的一半

```css
      position: absolute;
      left: 50%;
      top: 50%;
      margin-left: -50px;
      margin-top: -50px;
```

------



**方案3**

> ​	设置绝对定位或者固定定位，并且四个方向的值为0。（inset: 0;为4个方位为0的简写）
>
> ​	设置margin:auto 水平垂直居中。

```css
position: absolute; 
      left: 0;
      right: 0;
      top: 0;
      bottom: 0; */
      /* 这个就是上面的4个简写 */
      inset: 0;
      margin: auto; 
```

------



**方案4 定位搭配2D平移来实现**

> 其实方案2类似，只是将margin的平移回来 改成了2d平移回来。
>

```
.inner{
  width: 100px;
  height: 100px;
  background-color: pink;
  position: absolute;
  left: 50%;
  top: 50%;
  /* margin-left: -50px;
  margin-top: -50px; */
  transform: translate(-50%,-50%);
}
```

------



**方案5 使用flex布局实现**

> 可以将父元素开始flex，然后设置主轴居中，侧轴居中就行。
>
> > ​	display: flex;
> >
> > ​	justify-content: center;
> >
> > ​	align-items: center;

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .outer{
      width: 400px;
      height: 500px;
      border: 2px solid;
      /* 第四套水平垂直居中方案 */
      display: flex;
      justify-content: center;
      align-items: center;
    }
    .inner{
      width: 100px;
      height: 100px;
      background-color: pink;
    }
  </style>
</head>
<body>
  

  <div class="outer">
    <div class="inner"></div>
  </div>
</body>
</html>
```

------







##### 场景2：实现子元素的宽度与父元素一致

> ##### 			**由元素的内容撑开，实现宽度一致。**

**方案1 （变为块）**

> ​	将子元素变为块元素，并在宽度上设置100%。
>
> ​	**注意！**：存在问题，若继续给子元素设置padding或margin或borde，**子元素会溢出父元素**。
>
> ​	**解决，将设置宽度的100%去掉。**



**方案2（变为行内块）**

> ​	将子元素变为行内块元素，并在宽度等于父元素的宽度。
>
> ​	**注意！**：存在问题，若继续给子元素设置padding或margin或border，**子元素会溢出父元素**。
>
> ​	**解决，将宽度设置成父元素减去这些padding的宽度。**



**方案3（使用定位）**

> ​	给父元素和子元素添加定位，**子元素一定要设置绝对定位**。并且子元素在宽度上设置100%。
>
> ​	**注意！：**存在问题，若继续给子元素设置padding或margin或border，**子元素会溢出父元素**。
>
> ​	**解决：将设置宽度的100%去掉。并且子元素定位的左右值为0.（引出上下同理）**

```css
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .outer{
      width: 400px;
      height: 300px;
      background-color: pink;
      position: relative;
    }
    .inner{
      /* width: 100%;
      height: 100%; */
      /* width: 100%; */
      /* width: 380px; */
      /* display: inline-block; */
      /* margin: 10px; */
      border: 10px solid red;
      /* margin: 10px; */
      padding: 10px;
      background-color: blue;
      position: absolute;
      left: 0;
      right: 0;
      /* left: 20px;
      right: 20px;
      top: 10px;
      bottom: 10px; */
     
    }
  </style>
</head>
<body>
  <div class="outer">
    <span class="inner">123123123</span>
  </div>
</body>
</html>
```

​	

------



##### 场景3：实现遮罩层效果

> 可以将需要遮罩的元素外套一个父元素，并将父元素开启相对定位或者绝对定位。
>
> 再在子元素后加一个人任意元素，对这个元素开启绝对定位
>
> 必须在子元素上要加left0 top0，讲元素定位到父元素上
>
> > ​	如果想让整个屏幕遮住，可以直接对元素开启fixed定位
> >
> > ​	并且将定位的上下左右值设为0

```css
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    body{
      height: 3000px;
    }
    /* .navbar{
      height: 50px;
      background-color: yellow;
      position: fixed;
      left: 0;
      top: 0;
      right: 0;
    } */
    .outer{
      width: 500px;
      height: 400px;
      border: 2px solid;
      position: relative;
    }
    img{
      width: 100%;
      height: 100%;
    }
    .inner{
      background-color: rgba(0, 0, 0, .3);
      position: absolute;
      left: 0;
      top: 0;
      right: 0;
      bottom: 0;
    }
    .w{
      position: fixed;
      left: 0;
      top: 0;
      bottom: 0;
      right: 0;
      background-color: rgba(0, 0, 0, .3);
    }
  </style>
</head>
<body>



  <div class="outer">
    <img src="./案例讲解/img/hw1_main.png" alt="">
    <div class="inner"></div>
  </div>

  <button>按钮</button>
  <a href="http://baidu.com">百度</a>

  <div class="w"></div>
  <div class="navbar">导航</div>
</body>
</html>
```

------



#### 定位中的层次

> 定位的元素是有层次的，会**按照<body>**里面标签的**顺序进行重叠**，后写的元素定位覆盖前面的。
>
> > ​	当元素之间重叠的时候，**z-index** 较大的元素会覆盖较小的元素在上层进行显示。值可以为负数。



> **层次一般来说是兄弟元素之间比较。**
>
> **如果是父子元素比较，并且想将父元素置于子元素之上。**
>
> > ​	**子元素的值必须写负数，并且父元素不能写值才能实现。**
>
> 
>
> **如果z-inex值大的元素，依然没有覆盖掉z-index值小的元素，那么需要检查其包含块的层级！！！**

```css
.box2{
  width: 150px;
  height: 150px;
  background-color: pink;
  /* position: relative; */
  /* z-index: 2; */
  /* z-index: -1; */

}
```

------



### 怪异盒模型

> **浏览器的排版引擎使用三种模式：怪异模式（Quirks mode）、接近标准模式（Almost standards mode）、以及标准模式（Standards mode）**



> 控制元素是标准盒模型还是怪异盒模型
>
> > ​	标准盒模型 = content + padding +border + margin
> >
> > ​		其中content=width*height
> >
> > ​	怪异盒模型 = content + margin
> >
> > ​		其中 content=width*height+padding+border
> >
> > ​	设置了内边距和边框是不会在可见区域变大。



#### box-sizing

> ​	可以改变元素的盒模型
>
> ​	**box-sizing: border-box 将标准盒模型转换怪异盒模型**
>
> ​	**box-sizing: content-box 将标准盒模型转换怪异盒模型**
>
> 简单的理解 就是加了这个属性以后就不会在原本的宽高上在+上内边距和边框了

```css
box-sizing:border-box;
```

------



### 圆角

> **border-radius**允许设置元素的边框圆角。当使用一个半径时确定一个圆形，当使用两个半径时确定一个椭圆。这个（椭）圆与边框的交集形成圆角效果。
>
> 

**注意！中间没有逗号隔开！！！！**

> ​	**如果元素没有border和padding的时候，border-radius对背景颜色起作用。**
>
> ​	**如果元素没有border，但是有padding的时候，border-radius对padding起作用。**
>
> ​	**如果元素有border，border-radius对border起作用。**



> 顺序和外边距是一个道理: 左上角，右上角，右下角，左下角
>
> > ​	如果说需要写一个圆  就是将圆角的值设置为 原本宽高的一半 
> >
> > ​	原理：将设定一个值为给定值半径的圆，然后放入元素的左上角等位置，从而制造圆角。

```css
border-radius:10px 30px  50px 70px; 
```

------



## Day14_背景，精灵图，icon，包含块，BFC

### 背景样式

> CSS 背景和边框做的一些创造性事情。从添加渐变、背景图像到圆角，背景和边框可以解决 CSS 中的许多样式问题。

------



#### 背景颜色

> 会设置元素的背景色，属性的值为颜色值或关键字"transparent"二者选其一。



> **background-color**

```css
background-color: pink;
```

------



#### 背景图片

> ​	**背景图和图片的区别**  
>
> > ​		img标签会占据位置  背景图不会占位置 背景图会直到当前容器铺满
> >
> > ​		**给img用此css属性**，可以让img填满整个父元素容器。
> >
> > > ​			**object-fit:cover;**



> **background-image**
>
> ​	可以他添加过多张背景图片

```css
background-image: url(./atm.png);
background-image: url(image1.png), url(image2.png);
```

------



##### 背景图片的重复方式

> **`background-repeat`** [CSS](https://developer.mozilla.org/zh-CN/docs/Web/CSS) 属性定义背景图像的重复方式。背景图像可以沿着水平轴，垂直轴，两个轴重复，或者根本不重复。



> ​	**background-repeat**
>
> > ​		no-repeat: 不重复 
> >
> > ​		repeat-y: 垂直重复 
> >
> > ​		repeat-x: 水平重复

```css
background-repeat:no-repeat;
```

------



##### 背景图片的大小

>  设置背景图片大小。图片可以保有其原有的尺寸，或者拉伸到新的尺寸，或者在保持其原有比例的同时缩放到元素的可用空间的尺寸。



> ​		**background-size**
>
> ​			**两个值分别表示宽和高**
>
> ​				vh 当前的屏幕有多宽/高 那就100vh就是多少
>
> ​			**cover:同比例缩放 直到短边撑满**
>
> ​			**contain:同比例缩放知道长边撑满**

```css
background-size: 200px 10px;
background-size: 100% 100vh;
background-size:cover;
background-size:contain;
```

------



##### 背景图片的位置

> 此属性可以给每一个背景图片设置初始位置。这个位置是相对于由 [`background-origin`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-origin) 定义的位置图层的。



> ​	**background-position**
>
> ​		值是x 和 y  **正数往右边或者下边移动  负数往左边或者上边移动**
>
> ​		可以写方位任意一个位置  **left right top bottom center**
>
> ​		**值只写一个的时候，第二个值默认就是center**

```css
background-position:-50px -20px;
background-position:center;
```

------



##### 背景图片的位置起源

> 背景图片属性的原点位置的背景相对区域。
>
> 注意：当使用 [`background-attachment`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-attachment) 为 fixed 时，该属性将被忽略不起作用。

> ​	**background-origin**
>
> > ​		content-box 背景图片从内容区域开始
> >
> > ​		padding-box 背景图片从内边距位置开始  默认值
> >
> > ​		border-box 背景图片从边框位置开始

```css
background-origin:content-box;
```

------



##### 背景的裁剪

> 如果没有设置背景图片（[`background-image`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-image)）或背景颜色（[`background-color`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-color)），那么这个属性只有在边框（ [`border`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/border)）被设置为非固实（soild）、透明或半透明时才能看到视觉效果（与 [`border-style`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/border-style) 或 [`border-image`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/border-image) 有关），否则，本属性产生的样式变化会被边框覆盖。



> ​	**background-clip**
>
> > ​		content-box 背景从内容位置开始裁剪
> >
> > ​		padding-box 背景从内边距开始裁剪
> >
> > ​		border-box 背景从边框开始裁剪 默认的

```css
background-clip:content-box;
```

------



#### body和html的背景

> ​	浏览器的背景颜色是**先找html**是否有设置背景颜色 有就用它的。html没有的话**找body的背景**做窗口颜色
>
> ​    如果这两个都没有**不加**



#### 固定背景

此属性决定背景图像的位置是在视口内固定，或者随着包含它的区块滚动。

> ​	**background-attachment**
>
> > ​			**fixed**：表示背景相对于视口固定。
> >
> > ​			即使一个元素拥有滚动机制，背景也不会随着元素的内容滚动。



> ​				**scroll**：背景图片随着页面的滚动而滚动，默认值
> ​				**fixed**：背景图片不会随着页面的滚动而滚动
> ​				**local**：背景图片会随着元素的内容滚动而滚动

```css
/* 关键 属性值 */
background-attachment: scroll;
background-attachment: fixed;
background-attachment: local;

/* 全局 属性值 */
background-attachment: inherit;
background-attachment: initial;
background-attachment: unset;
```

------



#### 背景的简写

背景可以采用简写的方式，但是最好不要，容易让人看不懂。

```css
background: url(./atm.png) yellow  20px 20px/500px 500px no-repeat;
```

------



### 精灵图

又称雪碧图，sprites。就是把好多小的图片合并一张大图, 以该大图为背景图片的元素尺寸比较小,可以通过控制背景图片的位置,让元素上显示合适的图像。从而减伤用户请求服务器次数，达到提高性能的目的。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    a{
      text-decoration: none; 
      color: #000;
      width: 163px;
      height: 40px;
      background-color: yellow;
      display: block;
      text-align: center;
      line-height: 40px;
      /* 精灵图 雪碧图  sprites   https://www.saoban.cn/css-sprites.html*/
      /* background-image: url("./btn1.png"); */
      background-image: url("./css_sprites.png");
      background-repeat: no-repeat;
      background-position:0 -32px;
    }
    a:hover{
      background-position:0 4px;
      /* background-image: url("./btn2.png"); */
    }


    /* .logo1{
      width: 40px;
      height: 40px;
      display: block;
      background-color: yellow;
      background-image: url(./163_f2e_www_index20170701_images_sprite_img20211126.png);
      background-repeat: no-repeat;
      background-position: -160px 0;
    }

    .logo2{
      width: 40px;
      height: 40px;
      display: block;
      background-color: yellow;
      background-image: url(./163_f2e_www_index20170701_images_sprite_img20211126.png);
      background-repeat: no-repeat;
      background-position: -210px 0;
    } */
  </style>
</head>
<body>
  <a href="">按钮</a>

<!-- 
  <a href="" class="logo1"></a>
  <a href="" class="logo2"></a> -->
</body>
</html>
```

------



### icon图标

使用shortcut icon，为网页标题可以添加图标，此图标会缓存在用户本地，下次用户访问时，会直接显示。

```html
 <link rel="shortcut icon" href="./img/favicon.ico">
```



### 包含快

#### 包含快的概念

> 一个元素的尺寸和位置（包括定位中的层级？）经常受其**包含块**（containing block）的影响。
>
> 大多数情况下，包含块就是这个元素**最近的祖先[块元素](https://developer.mozilla.org/zh-CN/docs/Glossary/Block-level_content)**的[内容区域](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model#内容区域)，但也不是总是这样。

------



#### 包含块的影响

> 当一个元素宽高或者说**left right top bottom padding**..**设置百分比**的时候是**根据包含块content区域的宽高**来计算 

------



#### 根据包含块计算百分值

> **height、top、bottom设置百分比是根据包含块的content区域中height进行计算**
>
> **width、left、 right、padding、margin 设置百分比是根据包含块的content区域中width来进行计算**
>
> **注意！在怪异盒模型下的子元素如果设置百分比，只根据包含快的宽高来继承。只会计算包含快content中的width和height的百分比，不会加上padding和border。因为content=width*height+padding+border**

------



#### 如何确定包含块

>    1.当元素的position 值为static、relative 或 sticky或者说不写的时候它的包含块是最近的祖先块级元素（比如说 inline-block, block 或 list-item 元素）
>
>    2.当元素的position 值为absolute ，包含块是最近开启定位的祖先元素(除了static)，如果说所有的祖先都没有开启那包含块就是视口（初始包含块）
>
>    3.当元素的position 值为fixed 的时候 它的包含块就是视口（初始包含块）



> **备注：** 根元素 (<html>) 所在的包含块是一个被称为**初始包含块**的矩形。他的尺寸是**视口 viewport** (for continuous media) 或**分页媒体 page media** (for paged media).

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    *{
      margin: 0;
    }
    body {
      height: 3000px;
    }

    .outer {
      width: 500px;
      height: 400px;
      /* border: 20px solid; */
      /* padding: 20px; */
      background-color: yellow;
      position: relative;

    }

    .parent {
      width: 300px;
      height: 200px;
      background-color: aqua;
      /* display: inline; */

    }

    /* 
    包含块:基本上的情况包含块是父元素
      当一个元素宽高或者说left right top bottom padding..设置百分比的时候是根据包含块content区域的宽高来计算 
      height、top、bottom是根据包含块的高度进行计算
      width、left right padding margin 这些设置百分比是根据包含块的width来进行计算
      1.当position 值为static、relative 或 sticky或者说不写的时候它的包含块是最近的祖先块级（行内块）元素
      2.当position 值为absolute ，包含块是最近开启定位的祖先元素(除了static)，如果说所有的祖先都没有开启那包含块就是视口（初始包含块）
      3.当position 值为fixed 的时候 它的包含块就是视口（初始包含块）
    */
    .inner {
      width:50%;
      /* width: 100px;
      height: 100px; */
      /* width: 50%;
        height: 50%; */
      background-color: pink;
      /* position: static; */
      /* margin-top: 250px; */
      /* position: absolute; */
      position: fixed;

    }
  </style>
</head>

<body>
  <div class="outer">
    <div class="parent">
      <div class="inner">123</div>
    </div>
  </div>
</body>

</html>
```

------



### BFC

> **区块格式化上下文**（Block Formatting Context，BFC）是 Web 页面的可视 CSS 渲染的一部分，是块级盒子的布局过程发生的区域，也是浮动元素与其他元素交互的区域。



> **通俗来讲，BFC是文档流（normal flow）， 独立渲染区域，封闭，不会影响外面世界布局**。



**BFC有以下特点**：

> ​	1. 布局是从上至下的
>
> ​	2. 同一个BFC中的元素**上下外边距会重叠**（解决外边距重叠问题）
>
> ​	3. 计算BFC高度时，**会计算上浮动的高度**（因为float脱离了（半脱离）“文档流”，没有脱离“文本流”。解决浮动塌陷问题）
>
> ​	4. 计算BFC高度时，**不会计算上绝对和固定定位的高度**（因为这两完全脱离了文档流，会导致两者定位中高度坍塌的问题）
>
> ​	5. BFC区域**不会**与float元素**重叠**。它会忽视掉浮动元素的布局，与浮动元素会紧紧的挨在一起。（其他bfc就能与此浮动元素排列贴合。但是必须要其中浮动才行）

> ​			*备注：自己理解：文本流（text flow），概括地说其实就是一系列字符，是文档的读取和输出顺序，也就是我们通常看到的由左到右、由上而下的读取和输出形式。



**开启BFC最无隐患的做法**：

> **display: flow-root;**
>
> > ​		没有任何副作用，它的作用很单纯就是开启bfc。但是属性较新，可能有浏览器不支持。并且使用display以后，后面此元素就不能在使用这个属性，比如变成块元素等，会覆盖掉前属性。



> **overflow: hidden;**
>
> > ​		没有任何副作用，可以做以上溢出处理，但是缺点溢出部分会被隐藏掉。

------





## Day15_轮廓，元素的隐藏，三角形，梯形

### 轮廓

> 它和边框很像，但是轮廓不会占据布局中的位置，边框会占据。书写方式跟border类似，也可以简写。
>
> > 但是它**只能同时设定4个边的宽度**，不能像border一样分别设置。



#### **格式**

> ​	**outline-style:solid;**
>
> ​	**outline-color: rgba(0, 0, 0, 0.3);**
>
> ​	**outline-width:10px ;** 

```css
outline-style:solid;
outline-color: rgba(0, 0, 0, 0.3);
outline-width:10px; 
/* 简写方式 */
      outline: 10px dashed blue;
```



#### **清除轮廓的4个边宽度**

```css
outline:0
outline:none
```

------



### 元素隐藏的方案

> 我们可以将不想给用户显示的元素用CSS进行隐藏。
>
> ​	其实方案三就代替了方案二，但是可能存在浏览器兼容问题

​	

> ​	**方案一 不占位置**
>
> > ​		**display: none;**
>



> ​	**方案二 不占位置** 
>
> > ​		(让元素开启定位，并离开屏幕很远的地方，达到隐藏的效果)	
> >
> > ​		**position：fixed;**
> >
> > ​				**top:-1000px**



> ​	**方案二 占位置**
>
> > ​	（相当于把元素的透明度设置为0就隐藏了）
> >
> > ​		**opacity: 0;** 
>



> ​	**方案三 占位置的**
>
> > ​		**visibility: hidden;** 

------



### 三角形

> 可以利用边框来用css画出一个三角形

```css
  <style>
    div{
      width:0px;
      height: 0px;
      border: 50px solid blue;
      border-top-color: transparent;
      border-right-color: blue;
      border-left-color: transparent;
      border-bottom-color: blue;
    }
  </style>
```

------



### 梯形

> 梯形其实就是长方形被一个三角形覆盖了所产生的图片

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    div{
      width: 280px;
      height: 50px;
      margin:50px auto;
      border: 1px solid;
      position: relative;
    }
    div::before{
      content: '';
      width: 100px;
      height: 50px;
      display: block;
      background-color: #ffba00;
    }
    div::after{
      content: '';
      display: block;
      width: 0;
      height: 0;
      border:25px solid;
      border-top-color: #fff;
      border-right-color: #fff;
      border-left-color: transparent;
      border-bottom-color: transparent;
      position: absolute;
      left: 51px;
      top: 0;
      
    }
  </style>
</head>
<body>
  
  <div class="box">
  
  </div>

</body>
</html>
```

------



### 字体图标

> 可用使用一些字体图标代替图片，从而达到节约用户资源的目的。

> https://www.iconfont.cn/ 阿里图标库

------



> **引入格式：**

```html
 <link rel="stylesheet" href="./fonts/iconfont.css">
```

------





## Day16_案例讲解

> 详细请看Portfolio
>
> ​	后续要写心得体会。
>
> ​	特别是浮动，浮动塌陷，定位，绝对/固定定位高度塌陷。上下外边距塌陷的一些心得体会。





## Day17_HTML5与CSS3

### h5新增语义化标签

> ​     类似于div的标签只是更加有含义了 有语义了
>
> ​	 以下所有标签使用方式和div是一致的



####     header

> ​	头部标签 整个页面面的头部  或者某一块区域的头部  
>
> ​	类似于<div class='header'></div>



####     nav

> ​	导航标签  
>
> ​	类似于<div class='nav'></div>



####     main

> ​	主要内容区域  
>
> ​	类似于 <div class='main'></div>



####     footer

> ​	底部 
>
> ​	类似于 <div class='footer'></div>



####     menu

> ​	定义菜单栏的  暂时先别用
>



####     aside

> ​	定义侧边栏的
>



####     article

> ​	定义文章 评论 协议
>



####     section

> ​	定义某一个部分的 通常会用在大区域中的某一个小区域
>

  

```html
<header>
<nav></nav>
</header>

<main>
<aside></aside>
<article>我是文章内容
  <section></section>
</article>
</main>
<footer></footer>
```

------





### h5新增功能标签

#### 视频/音频标签

> 视频标签在不同的浏览器中 出现效果不一样的

```html
<video src=""></video>
<audio src=""></audio>
```

------



#### 进度指示标签

> ​	了解即可， 以后会用js来实现

```html
<progress value="5" max="10"></progress>
```

------



#### 文本的标注

> ​	类似拼音的功能，标注rt要写在后面比较好

```html
<ruby>
<p>大家好</p>
<rt>da jia hao</rt>
</ruby>
```

------



### CSS文本阴影

> ​	可以为文字添加阴影。可以为文字与 [`decoration`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/text-decoration) 添加多个阴影，阴影值之间**用逗号隔开**。每个阴影值由元素在 X 和 Y 方向的偏移量、模糊半径和颜色值组成。



**text-shadow:** 

​	**X Y 模糊度 颜色。中间没有逗号,除非多个阴影！！！**

```css
text-shadow:10px 10px 0px blue;
text-shadow: 0 0 1px red;
```

------



### CSS盒模型阴影

> ​	用于在元素的框架上添加阴影效果。可以在同一个元素上设置多个阴影效果，并**用逗号将他们分隔开**。该属性可设置的值包括阴影的 X 轴偏移量、Y 轴偏移量、模糊半径、扩散半径和颜色。



**box-shadow:**

​	**X Y 模糊度 阴影大小 颜色  inset(写了就是内阴影 不写就是外阴影)**

​	**中间没有逗号,除非多个阴影！！！**

```css
box-shadow: 10px 10px 10px 0 red inset; 

/* 用的比较多 */
box-shadow: 0 0 30px blue;
```

------





### 填充

> 可设置img或video等可替换元素的内容，应该如何适应到其使用高度和宽度确定的框。



​	**该属性使用在图片和视频上。**

​		**注意，必须才图片设置宽高百分比才起效，视频不用。**

> ​			object-fit:
>
> > ​				fill:充满整个容器 默认值
> >
> > ​				contain:等比例缩放知道短边撑满
> >
> > ​				cover：等比例缩放知道长边撑满 

> > > ​    	视频充满需要加以下，视频是浏览器默认生成的容器,它会两边留白
> > >
> > > ​      	object-fit: fill;

```css
img {
  width: 100%;
  height: 100%;
  object-fit: contain;
}

   video{
  width: 600px;
  height: 400px;
  border: 2px solid;
  object-fit: fill;
} 
```

------



### 滤镜

> 将模糊或颜色偏移等图形效果应用于元素。滤镜通常用于调整图像、背景和边框的渲染。



> **filter:滤镜**
>
> > ​     blur() 单位是像素 值越大 模糊程度越大
> >
> > ​     brightness() 当前的元素的亮度 100%默认的亮度  值越大越亮  越小越暗
> >
> > ​     grayscale() 当前元素的灰度  0-100%之间  值越大 越灰

```
img:first-of-type{
    filter: blur(10px);
    filter: brightness(100%); 
    filter:grayscale(1);
}
      
      
div{
  width: 200px;
  height: 200px;
  background-color: red;
  filter: brightness(100%); 
  filter:grayscale(0.4); 
}
```



### 字体图标的原理



**iconfont首先会创建一个字体族**

```css
@font-face {
  font-family: "hello";
  src: url('iconfont.woff2') format('woff2'),
      url('iconfont.woff') format('woff'),
      url('iconfont.ttf') format('truetype');

}
```



**然后设置总体样式**

```css
.iconfont {
  font-family: "hello";
  font-style: normal;
  font-weight: normal;
}
```



**然后对每个元素进行字体（我写的）和（它生成的）进行对应**

**注意由于在content里面无法书写"&#x"的内容，所以会写成 \ 的形式**

```CSS
.icon_gouwuche::after{
  content: '\e73d';
}
.icon_fangzi::after{
  content: "\e751";
}
.icon_hehe::after{
  content: "\e88f";
}
```

------



### 浏览器的前缀

> ​	一些CSS3属性在一些低版本的浏览器直接写这个属性是不支持的，但是加一些前缀有可能就支持，具体可查询caniuse这个网站。

比如：filter:blur(30px); 

**edge和谷歌以及safari浏览器的私有前缀，webkit内核的前缀**

```css
-webkit-filter: blur(30px);
```

**火狐内核** 

```css
-moz-filter:blur(30px);
```

**IE内核**

```css
-ms-filter: blur(30px);
```

**早些年的open** 

```css
-o-filter:blur(30px)
```

------

#### 一些前缀的用法

##### 处理ios端滚动卡顿问题 

```css
 -webkit-overflow-scrolling: touch;
```



##### 选择去除滚动条 

```css
main::-webkit-scrollbar{
	display: none;
}
```



### 引入CSS的方案

**方案一，直接引入**

> 在html页面用link引入

```css
<link rel="stylesheet" href="./aaa.css">
```



方案二，间接引入

> 在a（css） 中 引入b（css），然后将a用link引入html中

```css
/* 在a中引入b */
@import url(./bbb.css);
<link rel="stylesheet" href="./aaa.css">

```

------



### 过渡

> **类似与动画，但是不是动画**



**需要过度的属性** **transition-property:**

```css
transition-property:left,top,color,font-size,background-color,text-align,line-height; 

transition-property: all; 
```

------

**过渡的时间**  **transition-duration:**

```css
transition-duration:5s;
```

------

**过渡的延迟**  **transition-delay:** 

```css
transition-delay: 2s;
```

------

**过度的速度** **transition-timing-function**

ease：从慢到快到慢 

linear：匀速

steps(n)：n为过渡分为几步步骤

```css
transition-timing-function:steps(9)；
transition-timing-function:ease；
```

------

**简写**

> ​	**其中时间4s和延迟2s的顺序不能改变，其余可以改变**

```css
transition: all 4s 1s linear;
/* 最多的写法 */
transition:all .3s ease;
```

------





## Day18_CSS3的渐变/2D/3D

### 渐变

#### 线性渐变

> 线性渐变沿着直线改变颜色。
>
> 使用背景图这个属性来改变
>
> **语法是background-image开始，但是并不是只能改变图片的颜色，标签的背景颜色等也可以用这个改变。**



> **从图片的上到下依次渐变，默认是180deg旋转的**
>
> **表示从红色渐变到蓝色再黄色最后粉色**	

```css
background-image:linear-gradient(red,blue,yellow,pink);
```



> **向指定的方向渐变**
>
> > ​	**这里面一定要加 to，只有4个方位，没有center**

```css
background-image:linear-gradient( to right top,red,blue);
```



> **指定角度**
>
> > ​	**这里表示的是顺0时针的角度**

```css
background-image:linear-gradient(135deg,red,blue);
```



> **指定变色范围**
>
> > ​	**0-100之间是纯红色,**
> >
> > ​	**100到150之间的红色渐变到蓝色过程，**
> >
> > ​	**150-170是纯蓝色**
> >
> > ​	**170-200是蓝色渐变到黄色**
> >
> > ​	**200以后是纯黄色**

```css
background-image:linear-gradient(red 100px,blue 150px,blue 170px,yellow 200px);
```

------



#### 径向渐变

> 可以让颜色沿着图片的中心点向四周进行颜色渐变



> **颜色从图片中心点依次渐变**
>
> > ​	**红色到蓝色再到黄色**

```css
background-image: radial-gradient(red,blue,yellow);
```



> **指定中心的的形状进行渐变**
>
> > ​	**其中第一个值表示，图片沿着中心点Y轴方向的距离（直径 300px）**
> >
> > ​	**第二个值表示，图片沿着中心点X轴方向的距离（直径 100px）**

```css
background-image: radial-gradient(300px 100px,red,blue)
```



> **指定变色范围**

> 跟现象渐变一样，可以指定多少到多少px的渐变范围
>
> > ​	red后面的值表示从0到50px（半径）为纯红色
> >
> > ​	50px到100px（半径）红色渐变到蓝色
> >
> > ​	100px以后为纯蓝色
>
> ​	如果写了以上值又写了前面两个值，并且前面两个值指定的是圆形（或者直接写circle），那么其实前面两个值就没有意义了，除非是椭圆形才会由意义。

```css
background-image: radial-gradient(300px 300px,red 50px,blue 100px );
background-image: radial-gradient(circle,red 50px,blue 180px );
```

------



#### 重复渐变

> 表示颜色可以按照一定规律重复渐变，直线/径向的重复渐变



**直线的重复渐变**

> **属性名：background-image:repeating-linear-gradient（）**
>
> > ​	**其实就是属性名变了，里面的值跟直线渐变一样**

```css
background-image:repeating-linear-gradient(45deg,red 100px,blue 150px,yellow 200px);

background-image:repeating-linear-gradient(#000 0,#000 50px,#fff 50px,#fff 100px); 


```



**径向的重复渐变**

> **属性名：background-image:repeating-radial-gradient（）**
>
> > ​	**其实就是属性名变了，里面的值跟径向渐变一样**
> >
> > ​	**如果不填circle,前两个值还是表示圆的形状**

```css
background-image: repeating-radial-gradient(circle,red 0,red 20px,blue 20px, blue 40px);

background-image: repeating-radial-gradient(50px 60px,red 0,red 20px,blue 20px, blue 40px);
```

------



#### 渐变小案例

**按钮的渐变**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    /* .box1{
      width: 300px;
      height: 300px;
      border: 2px solid;
      background-image: linear-gradient(#fff 150px,#000 150px);
      border-radius: 50%;
    } */

    /* .box2{
      width:220px;
      height: 50px;
      border: 2px solid;
      background-image: linear-gradient(60deg,#ffba00 90px,#fff 90px);
    } */

    a{
      width: 120px;
      height: 40px;
      display: block;
      text-align: center;
      line-height: 40px;
      text-decoration: none;
      margin: auto;
      color: #fff;
      background-image: linear-gradient(90deg,rgb(118, 148, 118),rgb(7, 46, 7),rgb(118, 148, 118));
      border-radius: 2px;
      box-shadow: 2px 5px 10px rgba(100, 100, 100, .4);
    }
  </style>
</head>
<body>

  <a href="">按钮</a>


  <!-- <div class="box1"></div> -->

  <!-- <div class="box2">123123123</div> -->

  
</body>
</html>
```

------



### 2D变换

> **通用属性名：transform。只是里面会加不同的函数。**
>
> > ​	**记住，如果一个元素又多个transform这个属性，只有最后一个会生效。**
> >
> > ​	**注意！变形这个属性它对行内元素无效的，除非父元素开启flex布局，flex开启以后没有行内元素块元素区分**



#### 平移

> 平移可以将元素在水平和/或垂直方向上重新定位该元素。
>
> > ​	它不会脱离文档流的，它就相当再页面中移动了自己所在位置
> >
> > ​    它设置的百分比是根据自己本身元素的大小来的



> **transform: translate**
>
> > ​	**第一个值表示沿着元素左上角（或者元素中心点）往X轴移动的距离（像素），正值向右，负值向左**
> >
> > ​	**第二个值表示沿着元素左上角（或者元素中心点）往Y轴移动的距离（像素）正值向下，负值向上**

```css
transform:translateX(200px); 
transform: translateY(200px); 
transform: translateZ(200px);
transform: translateX(50%);
transform: translate(10px,100px);
```

------



#### 旋转

> transform: rotate(30deg);
>
> > 默认是沿着元素中心点进行旋转	
> >
> > 旋转单位 deg度  正数是顺势正方向旋转  负数时逆时针方向旋转

```css
transform: rotate(30deg);
```

------



#### 缩放

>  transform: scale(1.2);
>
> > 将元素以自身中心点进行等比例放大
> >
> > 默认自己大小是1倍，大于1就是变大  小于1就是缩小 但是不要低于0

```css
 transform: scale(1.2);
```

------



#### 倾斜

> transform: skew(30deg);
>
> > ​	将元素以自身中心点按照一定的角度进行倾斜
> >
> > ​	注意！单位是deg！
> >
> > ​	正值逆时针倾斜，负值顺时针倾斜
> >
> > ​	值为正负90和正负270的时候，元素在2D平面消失，因为变成一条线了

```css
transform: skew(30deg);
```

------



#### 改变变换的基点

> **平移，旋转，缩放，倾斜都是默认以元素的中心点进行的。我们可以将这个基点进行修改。**



> 属性名：transform-origin:
>
> > ​	里面值为X,Y,Z，可以写像素。
> >
> > ​	注意，这里的像素默认是以元素左上角为原点的
> >
> > > ​		X值表示沿着元素左上角往X轴移动的距离（像素），正值向右，负值向左
> > >
> > > ​		Y值表示沿着元素左上角往Y轴移动的距离（像素）正值向下，负值向上
> > >
> > > ​		Z值表示沿着元素左上角往Z轴移动的距离（像素）正值向我（靠近屏幕），负值向里（远离屏幕）
> > >
> > > ​		值也可以写成left right top bottom center，但是只能最多上下和左右进行两个组合（2d情况下，3d情况下可以写三个xyz）。

```css
transform-origin:right top;
transform-origin: center center -200px;
```

------



#### 变换的简写

> 由于变换有多种效果但是只有一个transform属性值，所以当我们向进行多种变换的时候，就只能进行简写。



> **简写方式，将不同变换以空格隔开**
>
> **注意简写的顺序调换效果会不同**
>
> > ​	比如要实现先平移后旋转的效果应该先写rotate(45deg)，再写translate(400px)
> >
> > > ​		原因，每个变换其实都是一个矩阵，新坐标=矩阵A* 矩阵B * 原坐标。
> > >
> > > ​		顺序是从后往前乘的，所以后面的变换会先出现。

```css
transform: translate(400px) rotate(45deg) scale(2);
```

------



#### 变换的案例

##### 音阶导航案例

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    * {
      margin: 0;
      padding: 0;
    }

    nav {
      width: 480px;
      height: 40px;
      margin: 50px auto;
    }

    .item {
      float: left;
      width: 120px;
      height: 40px;
      text-align: center;
      line-height: 40px;
      border: 1px solid;
      box-sizing: border-box;
      overflow: hidden;
    }

    a {
      display: block;
      width: 120px;
      height: 100%;
    }

    .up {
      width: 120px;
      height: 40px;
      background-color: pink;
      opacity: .4;
      transition: all .4s linear;
    }

    .item:hover .up {
      transform: translate(0, -100%);
    }
  </style>
</head>

<body>

  <nav>
    <div class="item">
      <a href="">首页</a>
      <div class="up"></div>
    </div>
    <div class="item">
      <a href="">首页</a>
      <div class="up"></div>
    </div>
    <div class="item">
      <a href="">首页</a>
      <div class="up"></div>
    </div>
    <div class="item">
      <a href="">首页</a>
      <div class="up"></div>
    </div>
  </nav>

</body>

</html>
```

------



##### 旋转八卦图案例

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    *{
      margin: 0;
      padding: 0;
    }
    .box{
      width: 300px;
      height: 150px;
      border: 2px solid black;
      border-top: 150px solid black;
      border-radius: 50%;
      margin: 50px auto;
      position: relative;
      transition: all 2s linear;
    }
    .box::before{
      content: '';
      width: 40px;
      height: 40px;
      background-color: #000;
      display: block;
      border-radius: 50%;
      border: 55px solid #fff;
      position: absolute;
      top: -50%;
     
   
    }
    .box::after{
      content: '';
      width: 40px;
      height: 40px;
      background-color: #fff;
      display: block;
      border-radius: 50%;
      border: 55px solid #000;
      position: absolute;
      right: 0;
      top: -50%;
    }
    .box:hover{
      transform: rotate(360deg);
    }
  </style>
</head>
<body>
  <div class="box"></div>
</body>
</html>
```

------



##### 缩放的案例

> 可以将元素的字体进行缩放，从而完成字体从无到有的状态。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    body{
      /* background-color: red; */
      background-color: #f5f5f5;

    }
    /* 163案例样式 */
    .box{
      width: 300px;
      height: 300px;
      border: 2px solid;
      overflow: hidden;
      margin: 50px auto;
      padding: 10px;
   
    }
    img{
      width: 100%;
      height: 100%;
      transition: all .3s linear;
    }
    .box:hover img{
      /* width: 120%;
      height: 120%; */
      transform: scale(1.2);
    }

    /* 怎么让文字低于12个像素 */
    p{
      text-align: center;
      /* font-size: 12px; */
      transform: scale(0.3);
    }
    
    
  </style>
</head>
<body>


  <p>我是文字</p>
  <!-- 163案例 -->
  <!-- <div class="box">
    <img src="https://nimg.ws.126.net/?url=http%3A%2F%2Fcms-bucket.ws.126.net%2F2023%2F0717%2Fce00637ej00rxwzs8000rc000cl0069c.jpg&thumbnail=453y225&quality=100&type=jpg" alt="">
  </div> -->
</body>
</html>
```

------



##### 下拉列表案例

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    *{
      margin: 0;
      padding: 0;
    }
    nav{
      width: 600px;
      height: 50px;
      border: 1px solid;
      /* margin: 50px auto; */
    }
    nav .item {
      width: 200px;
      height: 50px;
      float: left;
      border: 1px solid;
      box-sizing: border-box;
    }
    nav .item a{
      width: 200px;
      height: 50px;
      display: block;
      text-decoration: none;
      text-align: center;
      line-height: 50px;
    }
    ul{
      width: 200px;
      /* height:0;
      font-size: 0; */
      background-color: aqua;
      list-style: none;
      /* display: none; */
      transition: all 2s linear;
      opacity: 0;
      /* transform: scale(0); */
      /* transform-origin: top center; */
    }
    li{
      line-height: 50px;
    }
    a:hover + ul{
      /* height: 200px; */
      /* font-size: 16px; */
      opacity: 1;
      /* display: block; */
      /* transform: scale(1); */
    }
  </style>
</head>
<body>
  
  <nav>
    <div class="item">
      <a href="">新闻</a>
      <ul>
        <li>新闻1</li>
        <li>新闻2</li>
        <li>新闻3</li>
      </ul>
    </div>
    <div class="item">
      <a href="">歌曲</a>
      <ul>
        <li>歌曲1</li>
        <li>歌曲2</li>
        <li>歌曲3</li>
      </ul>
    </div>
    <div class="item">
      <a href="">电影</a>
      <ul>
        <li>电影1</li>
        <li>电影2</li>
        <li>电影3</li>
      </ul>
    </div>
  </nav>

  <p>段落标签</p>



</body>
</html>
```

------



##### 手风琴案例

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    *{
      margin: 0;
      padding: 0;
    }
    nav{
      width: 200px;
      margin: 50px auto;
    }
    .item{
      width: 100%;
      /* height: 20px; */
      border: 1px solid;
      padding: 10px 10px;
    }
  
    i{
      width: 20px;
      height: 20px;
      display: block;
      float: right;
      position: relative;
      transition: all .2s linear;
    }
    i::before{
      content: '';
      width: 2px;
      height: 15px;
      background-color: #000;
      display: block;
      position: absolute;
      left: 0;
      top: 0;
      bottom: 0;
      right: 0;
      margin: auto;
      transform: rotate(40deg);
      transform-origin:top center;
    }
    i::after{
      content: '';
      width: 2px;
      height: 15px;
      background-color: #000;
       position: absolute;
      display: block;
      left: 0;
      top: 0;
      bottom: 0;
      right: 0;
      margin: auto;
      transform: rotate(-40deg);
      transform-origin:top center;
      
    }
    .item:hover ul{
      /* height: 80px;
      font-size: 14px; */
      transform: scale(1);
      height: 100px;
    
    }
    .item:hover i{
      transform: rotate(180deg);
   
    }
    ul{
      background-color: brown;
      list-style: none;
      margin-top: 10px;
      height: 0;
      /* font-size: 0; */
      transform: scale(0);
      transition: all .3s linear;
      transform-origin: top center;

    }
    ul li{
      height: 30px;
      line-height: 30px;
      text-align: center;
    }
  </style>
</head>
<body>
  
  <nav>
    <div class="item">
      <span>一级菜单</span>
      <i></i>
      <ul>
        <li>二级菜单</li>
        <li>二级菜单</li>
        <li>二级菜单</li>
      </ul>
    </div>
    <div class="item">
      <span>一级菜单</span>
      <i></i>
      <ul>
        <li>二级菜单</li>
        <li>二级菜单</li>
        <li>二级菜单</li>
      </ul>
    </div>
    <div class="item">
      <span>一级菜单</span>
      <i></i>
      <ul>
        <li>二级菜单</li>
        <li>二级菜单</li>
        <li>二级菜单</li>
      </ul>
    </div>
    <div class="item">
      <span>一级菜单</span>
      <i></i>
      <ul>
        <li>二级菜单</li>
        <li>二级菜单</li>
        <li>二级菜单</li>
      </ul>
    </div>
  </nav>


</body>
</html>
```

------



### 3D变换

#### **开启3D环境**

> 要对子元素进行3D变换，首先要将父元素开启3D环境。
>
> > ​	以下属性要加在父元素上。
> >
> > ​	**注意！变形这个属性它对行内元素无效的，除非父元素开启flex布局，flex开启以后没有行内元素块元素区分**

```css
transform-style: preserve-3d;
```

------



#### **开启景深**

> 同样由于transform只有这一个属性，所以为了达到使元素同时具体多种变换，需要进行简写。
>
> **但是景深可以直接写出来**，不用写在transform里面，也可以简写加进去



> 并且，可以给父元素开启景深属性，或者单独给各个子元素开启景深属性，使得3D变换的效果感官上给更加明显。
>
> > ​	景深的值为像素，越大则表示我（屏幕）离这个元素越远，反之则更近
> >
> > ​	越远的效果表示在元素进行3D变换的时候，对于我（屏幕）的效果越小

```css
perspective: 100px;
transform: perspective(100px);
```

------



#### 3D平移

> 属性：
>
> > ​	translate3d（x，y，z） ，其中XYZ表示以XYZ轴平移的距离（像素

```css
transform: translate3d(200px,100px,20px) perspective(100px);
```

------



#### 3D旋转

> 首先要开启3D环境和景深。

> **属性：**
>
> > ​	rotate 3D (x,y,z,角度) ，其中XYZ表示XYZ轴，值由两个，1旋转，0不旋转 。

```css
transform: perspective(100px) rotate3D(1,1,0,50deg);
```

------



#### 3D缩放

> 缩放在3D的时候,Z轴缩放是不会变厚



> 属性
>
> > ​	X Y的值为倍数，例如原元素的多少倍
> >
> > ​	transform: scale3d(x,y,z)
> >
> > ​	transform: scaleX()
> >
> > ​	transform: scaleY()
> >
> > ​	transform: scaleZ()

```css
transform: scale3d(1,1.5,1)
```

------



#### 3D倾斜

> 在3D中倾斜只有XY轴，没有Z轴。



> 属性：
>
> > ​	X Y的值为角度deg。
> >
> > ​	transform: skew(x,y)
> >
> > ​	transform: skewX()
> >
> > ​	transform: skewY()

```css
transform:skewY(50deg)
```

------



#### 旋转图集

> 这个可以为以后的轮播图做准备



```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    body{
      background-color: #ddd;
      height: 800px;
      border: 2px solid;
    }
    .box{
      width: 200px;
      height: 150px;
      background-color: pink;
      position: absolute;
      left: 0;
      top: 0;
      right: 0;
      bottom: 0;
      margin: auto;
      transform-style: preserve-3d;
      transform:perspective(600px) rotateX(-20deg) rotateY(10deg);
      transition: all 3s linear;
      transform-origin: center center -200px;

      /* transform: rotateY(45deg); */
      
    }
    .box div{
      width: 200px;
      height: 150px;
      border: 2px solid;
      text-align: center;
      line-height: 150px;
      font-size: 30px;
      position: absolute;
      transform-origin: center center -200px;

      /* 隐藏背面的文字 */
      /* backface-visibility: hidden; */
    }
    .item1{
      background-color: #38a9ab;
    }
    .item2{
      background-color: orange;
      transform: rotateY(60deg);
    }
    .item3{
      background-color: brown;
      transform: rotateY(120deg);
    }
    .item4{
      background-color: violet;
      transform: rotateY(180deg);
    }
    .item5{
      background-color: rgb(89, 88, 122);
      transform: rotateY(240deg);
    }
    .item6{
      background-color: rgb(24, 87, 27);
      transform: rotateY(300deg);
    }
    body:hover .box{
      transform:perspective(600px) rotateX(-20deg) rotateY(720deg);
    }
  </style>
</head>
<body>
  <div class="box">
    <div class="item1">1</div>
    <div class="item2">2</div>
    <div class="item3">3</div>
    <div class="item4">4</div>
    <div class="item5">5</div>
    <div class="item6">6</div>
  </div>
</body>
</html>
```

------



#### 旋转立方体

> **旋转的时候可以xy旋转，也可以xyz一起旋转都好像能达到效果。**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    @keyframes animat{
      0%{
        transform: rotate3d(1,1,1,0deg);
      }
      100%{
        transform: rotate3d(1,1,1,360deg);
      }
    }
    body{
      border: 2px solid;
      height: 800px;
    }
    .box{
      width: 200px;
      height: 200px;
      position: absolute;
      left: 0;
      top: 0;
      right: 0;
      bottom: 0;
      margin: auto;
      transform-style: preserve-3d;
      /* transform: rotateY(65deg); */
      /* perspective: 200px; */
      /* transform: rotateY(20deg); */
      transition: all 3s linear;
      transform-origin: center center -100px;
      animation: animat 2s linear infinite;
    }
    .box div{
      width: 200px;
      height: 200px;
      font-size: 24px;
      text-align: center;
      line-height: 200px;
      position: absolute;
    }
    .box div:nth-of-type(1){
      background-color: pink;
      /* transform: rotateY(45deg); */
     
    }
    .box div:nth-of-type(2){
      background-color: gray;
      transform: rotateY(180deg) translateZ(200px);
    }
    .box div:nth-of-type(3){
      background-color: orange;
      transform-origin: right center;
      transform: translateX(-200px) rotateY(-90deg);

    }
    .box div:nth-of-type(4){
      background-color: green;
      transform-origin: left center;
      transform: translateX(200px) rotateY(90deg);
    }
    .box div:nth-of-type(5){
      background-color: brown;
      transform: translateY(-200px) rotateX(90deg);
      transform-origin: bottom center;
    }
    .box div:nth-of-type(6){
      transform: translateY(200px)  rotateX(-90deg);
      transform-origin: top center;
      background-color: orangered;
    }
    /* body:hover .box{
      transform: rotate3d(1,1,1,720deg);
    } */
  </style>
</head>
<body>
  <div class="box">
    <div>前</div>
    <div>后</div>
    <div>左</div>
    <div>右</div>
    <div>上</div>
    <div>下</div>
  </div>
</body>
</html>
```

------





### 动画

#### **创建动画帧**

> 首先要在开头css中定义这个动画帧
>
> > ​	@keyframes （空格）动画名字
> >
> > ​	from表示起始帧的效果，to表示结束帧的效果
> >
> > ​	中间多个步骤可以前面用百分比代替。

```css
@keyframes animat {
  from{
    transform: translate(0,0);
  }
  to{
    transform: translate(500px,0);
  }
}

@keyframes animat {
  0% {
    transform: translate(0, 0) rotate(0deg);
    background-color: pink;
    font-size: 16;
  }

  25% {
    transform: translate(300px, 0) rotate(90deg);
    background-color: yellow;
    text-align: right;
    font-size: 28px;
  }

  50% {
    transform: translate(300px, 300px) rotate(180deg);
    background-color: green;
    text-align: left;
    font-size: 36px;
  }

  75% {
    transform: translate(0, 300px) rotate(270deg);
    background-color: goldenrod;
    text-align: right;
    font-size: 48px;
  }

  100% {
    transform: translate(0, 0) rotate(360deg);
    background-color: pink;
    text-align: center;
    font-size: 16;
  }
}
```

------



#### 部分动画**属性**

> 这些属性是加到需要进行动画效果的元素的css样式中的，其实与变换的属性相似。



##### 动画的名字

> ​	**animation-name: 将引入前面创建的动画帧的名字**

```css
animation-name: animat;
```

------



##### 动画的时间

> 定义完整一个动画所需要的时间

```css
animation-duration: 4s;
```

------



##### 动画的延迟

> 定义动画启动时候的延迟

```css
animation-delay: 3s;
```

------



##### 动画结束的位置

> 定义动画结束时候的位置
>
> > ​	animation-fill-mode
> >
> > > ​		backwards: 结束的时候回到起点 
> > >
> > > ​		forwards: 结束停留在结束的位置

```css
animation-fill-mode: forwards;
```

------



##### 动画执行的次数

> 定义动画需要被执行几次
>
> > ​	animation-iteration-count
> >
> > > ​		值写数字次数
> > >
> > > ​		或infinite: 表示无限执行

```css
animation-iteration-count:6;
```

------



##### 动画的速度

> 定义动画执行的速度变换
>
> > ​	animation-timing-function:
> >
> > > ​		ease：从慢到快再到慢
> > >
> > > ​		linear：匀速
> > >
> > > ​		steps(5)：里面填数字，表示走几步，类似钟表可以使用这种

```css
animation-timing-function:steps(5);
animation-timing-function:linear;
```

------



##### 动画执行的方向

> 动画执行的一个方向
>
> > ​	animation-direction：
> >
> > > ​		 alternate: from - to - from - to
> > >
> > > ​     	reverse: to-from 
> > >
> > > ​     	alternate-reverse: to-from-to-from

```css
animation-direction:alternate-reverse;
```

------



##### 动画的播放状态

> 这种状态一般配合JS使用
>
> > ​	animation-play-state:
> >
> > > ​		paused: 停止动画 
> > >
> > > ​		running: 运行动画 

```css
animation-play-state:paused;
```

------



##### 动画简写的方式

> 可以做了解，还是可以完整写出来表示清楚点。
>
> > ​	其中与变换的简写一样，动画时间与延迟时间不能交换顺序
> >
> > ​	animation: animat（动画名字） 1s（动画时间） 2s（延迟时间） infinite（执行次数） alternate-reverse linear（执行方向）;



```css
animation:animat 1s 2s infinite alternate-reverse linear;
```

------



#### 第三方库

> 这里介绍的是animate，这个css第三方库的使用
>
> > ​	主要是为元素的进场和退场加入动画



**官方网站**：https://animate.style



**使用方式**

> ​	1. 下载它的CSS样式
>
> ​	2. 并且在开头引入
>
> > ​		注意，需要引出在我们css样式的前面，防止我们写的css样式把它的覆盖掉。
>
> ​	3. 在我们所需要添加动画的元素中加入它的默认类（animate__animated），
>
> ​	4. 再加入动画的类目（这个可以直接去到它的官网复制这个类名）
>
> > ​		其实跟字体图标的引入方式是一样的。

------



#### 时钟案例

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    @keyframes animat{
      0%{
        transform: rotate(0deg);
      }
      100%{
        transform: rotate(360deg);
      }
    }
    .box{
      width: 200px;
      height: 200px;
      border-radius: 50%;
      border: 1px solid;
      position: absolute;
      left: 0;
      top: 0;
      bottom: 0;
      right: 0;
      margin: auto;
    }
    .c{
      width: 20px;
      height: 20px;
      background-color: #ddd;
      border-radius: 50%;
      position: absolute;
      left: 0;
      top: 0;
      bottom: 0;
      right: 0;
      margin: auto;
      z-index: 1;
    }
    .s{
      width: 2px;
      height: 80px;
      background-color: aquamarine;
      position: absolute;
      left: 50%;
      top: 20px;
      margin-left: -1px;
      transform-origin: bottom center;
      animation: animat 60s steps(60) infinite;
    }

  </style>
</head>
<body>
  <div class="box">
    <div class="c"></div>
    <div class="s"></div>
  </div>
</body>
</html>
```

------



#### 行走的人案例

> 这里相当于是再动画中加入背景图片， 然后每一帧用步数来切换，将背景图片的位置移动，从而达到效果。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    @keyframes animat {
      0%{
        background-position: 0 0;
      }
      100%{
        background-position: -1040px 0;
      }
    }
    div{
      height: 296px;
      width: 130px;
      background-color: #ddd;
      margin:50px auto;
      background-image: url("./帧动画.png");
      background-repeat: no-repeat;
      animation: animat 1s steps(8) infinite;
    }
  </style>
</head>
<body>
    <div></div>
  
</body>
</html>
```

------



#### 进场/退场动画

> 以后配合JS，我们可以对部分元素进行进场和退场动画的设计，也可以使用第三方库

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    @keyframes ant {
      0% {
        top: -800px;
      }
      20% {
        right: 30px;
        top: 100px;
      }
      50%{
        transform: scale(0.3);
      }
      60%{
        transform: scale(1);
      }
      70%{
        transform: translate(0,-90px);
      }
      100%{
        transform: translate(0,0);
      }
    }

    .box {
      width: 200px;
      height: 300px;
      background-color: #ddd;
      position: fixed;
      animation: ant 1s linear;
      right: 30px;
      top: 100px;
    }
  </style>
</head>

<body>
  <div class="box">我是一个商品</div>
</body>

</html>
```

------





## Day19_flex布局

### 概念

> 一种新的布局方式，会比flot和position好用很多
>
> 将当前元素开启flex 弹性盒子 当父元素开启了**弹性盒子**以后 子项变成了**弹性项目**
>
> > ​    当开启flex布局以后  会生成两个轴,一个是主轴 跟主轴对应就是侧轴

------



### 主轴轴向的改变

> **特点：**
>
> 1. 当一个元素开启了弹性盒子,它和里面的子元素就不分块级和行内元素了
>
> 2. 不管是自己还是弹性项目都不会脱离文档流
>
> 3. 它的弹性项目默认会沿着主轴方向排列



> **属性：**
>
> > ​	**flex-direction:**
> >
> > > ​		row: 水平方向 从左至右 默认的
> > >
> > > ​		row-reverse: 水平方向 从右至前排列
> > >
> > > ​		column: 垂直方向 从上至下的 
> > >
> > > ​		column-reverse: 垂直方向 从下至上

------



### 主轴方向的对齐方式

> 弹性项目在主轴上的对齐方式



> **属性：**
>
> **justify-content:**	 
>
> > ​		**flex-start**: 在弹性盒子的的起点位置排列
> >
> > ​		**flex-end**：在弹性盒子的的结束位置排列
> >
> > ​		**center**：在弹性盒子的居中位置紧密排列
> >
> > ​		**space-between**: 在每行上均匀分配弹性元素。相邻元素间距离相同。两端对齐
> >
> > ​			每个多余空间的值 = 剩余空间的值 除以（n-1）n为多少主轴上的子元素数量。
> >
> > ​		**space-around**: 多余的空间均匀分配给每一个弹性项目的**两边**
> >
> > ​				弹性项目两边多余空间的值 = 剩余空间的值 除以（n*2）
> >
> > ​		**space-evenly**：对于的空间均匀分配给每一个相邻子项目**之间**
> >
> > ​				弹性项目两边多余空间的值 = 剩余空间的值 除以（n+1）

------



### 主轴换行

**前提概念**

> ​	当子弹性项目总的宽度超过来**弹性盒子宽度**时的时候它会默认进行压缩
>
> > ​		**注意！**就算改变主轴位置，**不会默认**沿着弹性盒子（父元素）进行压缩。可以后续通过压缩属性进行压缩
> >
> > ​		但是如果**子元素过多**，压缩后也会**溢出**父元素的范围



**换行**

> 表示在主轴方向是否换行，默认不换行
>
> ​	**flex-wrap:**
>
> > ​		 nowrap: 不换行 自动压缩
> >
> > ​     	wrap: 换行,当子弹性项目总的宽度超过来弹性盒子的时候会换行
> >
> > ​     	wrap-reverse: 换行并且反转



**指定几个个元素换行**

> 只需要在第几个元素后加个div，然后设置这个div的宽度为100%就行了



**换行与改变主轴简写**

```css
flex-flow:wrap row-reverse;
```

------



### 侧轴方向的对齐方式

#### 针对单行的情况



**属性**

​	**align-items:**

> ​		flex-start：侧轴的起点位置
>
> ​		flex-end: 侧轴的结束位置
>
> ​		center：侧轴的居中位置
>
> ​		stretch: 侧轴方向拉伸 默认值（如果不给子元素设置高度或者宽度）		

------



#### 针对多行的情况



**属性（其实与主轴的对齐类似）**

​	**align-content:**

> ​		flex-start: 所有东西排列到弹性盒子侧轴的起始位置
>
> ​		flex-end: 所有东西排列到弹性盒子侧轴的结束位置
>
> ​		center: 所有东西排列到弹性盒子侧轴的居中位置
>
> ​		space-between: 在侧轴上两端对齐，剩余空间分配给相邻的每行距离
>
> ​		space-around：将剩余的空间均匀分配给侧轴上每一行的两边
>
> ​		space-evenly: 将剩余的空间分配给侧轴每一行的上下空间
>
> ​		stretch: 默认值，将剩余空间分配给 每一行的下边，如果说没有高度就是拉伸

------



### 弹性项目拉伸

> **一般来说拉伸和压缩都是针对主轴而言的，并且拉伸压缩一般是针对子元素（弹性项目而言的）**



**属性**

​	**flex-grow: 1**

> ​		弹性项目在主轴上的拉伸 按比例均匀分配的  拉伸不写默认是0



> ​		给当前子元素拉伸多少的**计算公式**：剩余空间 乘以 （当前子元素flex-grow的数字 除以 父元素中flex-grow里面数字的总数）

------



### 弹性项目压缩

> **一般来说拉伸和压缩都是针对主轴而言的，并且拉伸压缩一般是针对子元素（弹性项目而言的）**



**属性**

​	**flex-shrink: 1**

> ​		主轴上的一个压缩,当子项目超出弹性盒子的范围就可以压缩,
>
> ​		但是如果设置了行高，该属性无效
>
> ​		默认不写的时候1  这个值基本不设置 默认是1就可以了



> ​		给当前子元素拉伸多少的**计算公式** 待补充



------



### 单个弹性项目（子元素）在侧轴的对齐

> **单个子弹性项目在侧轴上的对齐方式,它的所有值和align-items是一模一样的**
>
> ​	**这里是针对的单个子元素，而align-items针对的是单行侧轴的所有子元素**



**属性**

​	**align-self:** 

> ​		flex-start：侧轴的起点位置
>
> ​		flex-end: 侧轴的结束位置
>
> ​		center：侧轴的居中位置
>
> ​		stretch: 侧轴方向拉伸 默认值（如果不给子元素设置高度或者宽度）

------



### 单个弹性项目（子元素）的基础尺寸

> 可以对单个子元素定义在主轴上基础尺寸 
>
> > ​	**但是！**会把原本主轴上的尺寸给**覆盖掉**



**属性**

​	**flex-basis:**

> ​		里面填多少像素单位即可

```css
flex-basis:300px;
```

------



### 简写方式

不推荐简写，一般只在弹性项目（子元素）上进行拉伸的时候进行简写



**属性**

​	 **flex:拉伸 压缩 基础尺寸**

> ​		拉伸和压缩的值原本拉伸或者压缩的值 
>
> ​		一般都单写拉伸，比如第二个，就是对子元素拉伸比例为多少

```css
flex: 1 1 300px;
flex: 1
```

------



## Day20_变量，计算函数，媒体查询，自适应布局，dpr屏幕

### 变量

> 变量是有作用域：
>
> > ​    作用域：作用的范围
> >
> > ​    在当前的元素的选择器中定义的变量，它只能在**当前元素**和**后代元素**中使用
> >
> > ​    当使用变量的时候，会先在当前的作用域中查找，如果没有就往上层查找，直到找到根标签



#### **定义变量**

> 全局变量：在根标签中定义变量  
>
> 局部变量：在除跟标签中定义的变量

```css
--w:200px;
--b:20px solid blue;
--sz:36px;
--ma:50px auto;
```



#### **使用变量**

```css
width: var(--w);
height: var(--w);
border: var(--b);
font-size: var(--sz);
margin: var(--ma);
```

------



### 计算函数

> 可以在声明 CSS 属性值时执行一些计算。它可以用在如下场合：<length>、<frequency>, <angle>、<time>、<percentage>、<number>、或 <integer>。



> **注意点：运算符两边必须有空格**
>
> **格式：**	
>
> ​	**calc();**

```css
width: calc(200px + 100px + 20px); 
width: calc(200px - 20px); 
width: calc(200px * 2); 
width: calc(200px / 2); 
```

------



### 媒体查询

> 通过**媒体查询**（**Media queries**），可以根据各种设备特征和参数的值或者是否存在来调整您的网站或应用。



> **格式：**
>
> > ​	**screen：所有电脑 平板 手机屏幕**
> >
> > ​    **min-width:最小宽度 包含**
> >
> > ​    **max-width:最大宽度 包含**



> **1. 直接书写在不同尺寸下的不同样式表现**

```css
/* 
  <= 750 红色
  大于 750 并且小于等于1200是 蓝色
  大于1200 是粉色
*/

@media screen and (min-width:1200px) {
  body{
    background-color: pink;
  }
}

@media screen and (min-width:750px) and (max-width:1200px){
  body{
    background-color: blue;
  }
}

@media screen and (max-width:750px) {
  body{
    background-color: red;
  }
} 
```



> **2. 也可以根据不同尺寸引用不同的外部样式**

```css
<!-- 指定不同的屏幕使用不同的外部引用样式 -->
<link rel="stylesheet" href="./index1200.css" media="screen and (min-width:1200px)">

<link rel="stylesheet" href="./index750_1200.css" media="screen and (min-width:750px) and (max-width:1200px)">

<link rel="stylesheet" href="./index750.css" media="screen and (max-width:750px)">
```

------



#### 媒体查询案例

```css
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <link rel="stylesheet" href="./index1200.css" media="screen and (min-width:1200px)">
  <link rel="stylesheet" href="./index750_1200.css" media="screen and (min-width:750px) and (max-width:1200px)">
  <link rel="stylesheet" href="./index750.css" media="screen and (max-width:750px)">
</head>
<body>
  <header>
    <div class="logo">logo</div>
    <nav>
      <a href="">首页</a>
      <a href="">资讯</a>
      <a href="">会员</a>
      <a href="">推荐</a>
    </nav>
  </header>
</body>
</html>
```

------



### 自适应布局

> ​	设计稿只有一份，比如是375的设计稿
>
> ​		一个元素 100px + 100px  fz 24px
>
> ​		当屏幕变大 你的尺寸应该变大 屏幕变小尺寸应该变小
>
> ​		尺寸大于375px  100+ fz 24+
>
> ​		小于375  100- fz 24-
>
> ​	从而起到针对不同屏幕的大小，内容进行自动缩放。



#### rem与em

> ​	rem:它是根据根元素的字体大小来的，1rem=根元素的字体大小。
>
> ​	em:是根据自己字体大小，如果自己没有字体大小那就找最近的祖先元素字体大小，如果祖先都没有，那就是浏览器默认的字体大小。

------



#### 视口

> 移动端里面有视口概念:
>
> > ​	布局视口：在移动端默认有一个布局视口它是980px 它的作用就是布局的时候使用
> >
> > ​	视图视口：设备的视口大小
> >
> > ​	理想视口：当布局视口等于视图视口的时候它就是属于理想视口



> content="width=device-width": 布局视口等于设备视口 
>
> > ​	user-scalable=yes: 用户是否可以缩放 yes允许 no是不允许
> >
> > > ​		但是这个在一些浏览器中无效
> >
> > ​	maximum-scale=1, 最大缩放到1倍
> >
> > ​	minimum-scale=1，最小缩放到1倍
> >
> > ​	initial-scale=1，初始缩放比



> 以下命令就是规定屏幕的视口宽度等于设备的宽度，并且初始缩放位1.
>
> ​	写移动端的时候这句话必须要加上

```css
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

------



#### 补充meta

##### 字符编码

```css
<meta charset="UTF-8">
```



##### 网页关键字

> ​	网页的关键字 网页的seo使用

```css
<meta name="keywords" content="电商,衣服,电脑,商城,手机"/>
```



##### 网页的描述信息

> ​	对于网站的一些描述性信息，用于优化seo

```css
<meta name="description" content="这是一个电商网站"/>
```

------



#### 媒体查询+rem

> ​	可以根据不同媒体查询，判定不同屏幕。然后对于不同屏幕下的设定一个标准字体大小。然后后续的宽高等元素大小就根据这个基准的字体大小用rem表示。
>
>  原因：不同尺寸下 1rem = 不同的基准字体大小
>
> ​	当我们确定在多少屏幕尺寸的环境下编写时，只需要将多少px的转换成针对与当前基准字体大小的rem就行
>
> ​	1 rem = 32 px 就是32px就是基准字体大小，所以 1px = 0.03125 rem
>
> ​	如果我们要将某个元素的width设定为80px，只需要80px * 0.03125 rem = 2.5 rem，这样在其他媒体查询下，就可以同比例放大或者缩小
>
> ​	缺点：需要写很多媒体查询，并且放大缩小的画面不具备连贯性，还需要计算rem

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    @media screen and (min-width:320px){
        html{
          font-size: 32px; 
        }
    }
    @media screen and (min-width:375px){
        html{
          font-size: 37.5px;  
        }
    }
    @media screen and (min-width:390px){
        html{
          font-size: 39px;
        }
    }
    @media screen and (min-width:414px){
        html{
          font-size: 41.4px;
        }
    }

    div{
      width: 2.66666666rem;
      height: 2.66666666rem;
      background-color: pink;
      font-size: 0.64rem;
    }
  </style>
</head>
    
<body>
  <div>我是文字</div>
</body>
</html>
```

------





#### flexible+rem

> ​	由于媒体查询+rem的方法需要针对不同的屏幕写不同的基准字体大小，并且字体大小不好定义，所以可以用flexibl插件+rem的方式
>
> ​	这种方式其实就引入这个插件，这个插件它会自动给html元素设置一个字体大小，是屏幕是10分之1。就是默认基点的字体大小，就可以直接根据这个基点字体大小写宽高了。
>
> ​	原理同第一种

​	

```css
<!-- 1.引入flexiblejs文件 通过js将屏幕分成10等分 它会自动给html元素设置一个字体大小，是屏幕是10分之1-->

<script src="./flexible.js"></script>

<style>
    div{
      width: 2.666666666rem;
      height: 2.666666666rem;
      font-size: 0.64rem;
      background-color: pink;
      /* margin-left: .853333rem; */
      margin-left: .8533rem;
      margin-top: 1.28rem;  
	}
</style>
```

------



#### vw+rem

> css3中引入vw属性，从而刚刚好可以代替掉flexible插件的作用。
>
> > ​	vw表示的是视图宽度  100vw等于当前视图的宽度
> >
> > ​	vh表示的视图的高度  100vh等于当前屏幕的高度
> >
> > ​	这样把基准字体设置为10 vw，就等于原理的1/10的大小。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    html{
      font-size: 10vw;   
    }
    div{
      width: 2.666667rem;
      height:2.666667rem;
      background-color: pink;
      font-size: .64rem;
    }
  </style>
  
</head>
<body>
  <div>哈哈</div>
</body>
</html>
```

------



#### 纯vw

> ​	最后，我们可以根据设计稿的大小，直接使用vw来进行自适应布局。
>
> ​	比如，在375尺寸设计稿中，100vw = 375px，那么1px = 0.26666 vw
>
> ​	那么，在375设计稿中，100*100 fz24px ，就是等于26.66 vw * 26.66 vw fz6.39 vw。从而实现自适应
>
> ​	最后只需要在插件px2vw转换中提前设置好屏幕的宽度，让插件自动计算出即可。

```css
    div{
      width: 26.66667vw;
      height: 26.66667vw;
      font-size: 6.4vw;
      background-color: pink;
    }
```

------



### dpr

> **设配 分辨率**
>
>    **设备分辨率指的是物理像素**
>
>    **我们css中逻辑像素 css像素**
>
>    **逻辑像素/物理像素 = dpr**
>
> 
>
> ​	**造成这样的原因，就是物理像素数量可以高于逻辑像素的数量。因为物理像素越多，产生的图片就越真实，鲜艳。**
>
> ​	**造成的问题就是，同样尺寸大小的图片等，放在dpr屏幕（移动设备）下，显示的效果就不是很精细。**

------



#### 二倍图

> ​	为了解决上述dpr屏幕问题，我们可以根据dpr的比例来选择不同的比例图片。比如 逻辑像素和物理像素的比位1比2时，我们就可以使用二倍图放在dpr屏幕下，达到效果，同理，1比3时使用3倍图。

------



## Day21_移动电商案例讲解

> ​	需要后续优化和写心得。
