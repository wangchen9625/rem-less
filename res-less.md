#res
##概念
###单位有px  em  rem
em是根据父级元素的文字大小为依据
rem基准与html元素的字体大小
优点:可以修改html里面文字大小来改变页面中元素的大小  可以整体控制
[01基础.html案例](01基础.html)
###媒体查询
```
@media mediatype and|not|olty (media feature) {
            
}
```
1.用@media开头 
2.mediatype 
all:所有设备   
print:用于打印机和打印预览   
screen:用于电脑屏幕,平板,手机   
3.关键字 and not only 关键字后面的空格**不能省略**
and 多个媒体属性链接一起,相当于 且 的意思
not 排除
only    当且仅当
4.media feature 媒体特性 必须要小括号包含
max-width 最大可见区域宽度
min-width 最小可见区域宽度
width 可见区域宽度

ex:最大的宽度是800像素,设置样式
```
@media screen and (max-width:800px){
    body{
        background-color: pink;
    }
}
```
[根据页面大小改变颜色](03根据页面大小改变颜色.html)
###引入资源
```
<link rel="stylesheet" href="style320.css" media="screen and (min-width: 320px)">
<link rel="stylesheet" href="style640up.css" media="screen and (min-width: 640px)">
```
[05引入资源](05引入资源.html)
##less
###变量
```JavaScript
@color:purple;
@font14:14px;
body{
    background-color:@color;
}
```
###嵌套
标签嵌套 
```JavaScript
header{
    width: 200px;
    height: 200px;
    background-color: pink;
    a{
        color:red;
    }
}
```
伪类需要加一个'&'如下:
```JavaScript
.weilei{
    a{
        //伪类需要加一个&
        &:hover{
            color:blue;
        }
    }
}
```
```JavaScript
nav{
    .logo{
        color:green;
    }
    &::before{
        content:"伪类选择器before";
    }
}
```
###运算
两个数运算, 一个有单位,另一个没有单位,以有单位为准
如果两个都有单位,且单位还不一样,结果以第一个单位为准
除法的时候要带括号()
```JavaScript
@border: 5px + 5

div{
    width:200px -50;//-->150px
    height:(200px -100) * 2//-->200px
    border:@border solid red;
}
```
```JavaScript
h1{
    width:(82 / 50rem);//要括号才可以 不加括号不行 除法
    hegiht: 82 / 50rem;//这是错误的示范
}
p{
    width:(100px / 50rem);//-->2px
}
```
