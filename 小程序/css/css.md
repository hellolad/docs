#### 选择器

```css
/*包含选择器 作用于.first下的所有后代*/
.first li {} 

/*子选择器 作用于.first下的第一代后代*/
.first>li

/*通用选择器 作用于html下的所有元素*/
*{}

/*分组选择符 用逗号表示*/
h1, span

/*权重*/
/*标签选择器的权重为1 类选择符的权重为10 ID选择符的权重最高为100 权重越搞的优先显示 继承的权重最低*/
/*内联样式 > 嵌入样式表 > 外部样式表*/

/*重要性*/
p{color: red!important;}

```

#### 字间距

```css
/*文字间距*/
h1 {
   letter-spacing: 20px;
}
/*单词中间间距*/
h1 {
    word-spacing: 20px;
}
```

#### 块状元素居中

```css
h1{
    text-align: center;
}
```

##### 元素分类

```css
/*块状元素*/
/*每个块级元素都从新的一行开始，并且其后的元素也另起一行。（真霸道，一个块级元素独占一行）*/
/*元素的高度、宽度、行高以及顶和底边距都可设置。*/
/*元素宽度在不设置的情况下，是它本身父容器的100%（和父元素的宽度一致），除非设定一个宽度。*/
div, p, h1...h6, ol, ul, dl, table, address, blockquote, form

/*内联元素(行内元素)*/
/*
1. 和其他元素都在一行上；
2. 元素的高度、宽度及顶部和底部边距不可设置；
3. 元素的宽度就是它包含的文字或图片的宽度，不可改变
*/
a, span, br, i, em, strong, label, q, var, cite, code

/*内联块状元素*/
/*和其他元素都在一行上；*/
/*元素的高度、宽度、行高以及顶和底边距都可设置。*/
img, input


```

#### 流动模型 浮动模型 层模型

```swift
// html默认的的布局模式 就是 流动模式

// 浮动模型：float

// 层模型
/**
1. absolute: 绝对定位
这条语句的作用将元素从文档流中拖出来，然后使用left、right、top、bottom属性相对于其最接近的一个具有"定位属性"的父包含块进行绝对定位。如果不存在这样的包含块，则相对于body元素，即相对于浏览器窗口。

2. relative: 相对定位
需要设置position:relative（表示相对定位），它通过left、right、top、bottom属性确定元素在正常文档流中的偏移位置。相对定位完成的过程是首先按static(float)方式生成一个元素(并且元素像层一样浮动了起来)，然后相对于以前的位置移动，移动的方向和幅度由left、right、top、bottom属性确定，偏移前的位置保留不动。\

3. fixed: 固定定位
与绝对定位类似，但是他不受文档流的影响，始终浮动在哪个位置。并且不受滚动条的滚动而改变。

4. 相对定位和绝对定位的组合使用 作用于相对于某个元素进行定位.
前提是：参照元素是定位元素的父级元素,给父元素设置position: relative. 子元素position: absolute.

*/
```



##### 不定宽块状元素 水平居中

```css
/*
	通过设置text-algin：center设置块状元素内的元素居中
*/
```

##### 定宽元素 水平居中

```css
div{
    border:1px solid red;
    width: 200px;
	margin: 0 auto;
}
/*通过设置margin: 0 auto 来设置定宽元素的居中*/
```

 ##### 定高元素 垂直居中

> 设置line-height



#### 水平垂直居中

```css
view {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  position: absolute;
  top: 40%;
}
```



