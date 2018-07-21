 相关视频链接：https://www.bilibili.com/video/av8481988/?p=5

相关github地址：https://github.com/soyaine/JavaScript30

做题思路：

（1）监视input，当有change事件或mousemove事件发生的时候，就调用函数handleUpdate（）；

（2）用js改变css属性：document.documentElement.style.setProperty(" 某css属性"，新值）；//即jQuery中的$().css();

（3）用js获取data-自定义的属性：xx.dataset.sizing;  //获取xx标签内的自定义属性data-sizing的值

 

需要了解的知识点：

1，html5部分

（1）input属性

input的输入类型现在已经有email, url, number, range, Date picker(date, month, week, time, datetime,  datetime-locale), search, color

但是主流浏览器中Firefox全支持，chrome不支持color（其他浏览器支持的不多）

type属性	用途	用法	截图
email	e-mail地址的输入域，在提交表单的时候，会自动验证Email的值	
Email : <input type="email"  name="user_email"/>

number	用于包含数值的输入域，可设置对所接受的数字的限定	
Points : <input type="number"  name="points" min="1" max="100" step="10" value="55"/>
<!-- max 允许的最大值； min 允许的最小值； step 规定合法的数字间隔； value 规定的默认值-->

 

range	用于包含一定范围数字值的输入域，显示为滑动条	
<input type="range"  name="points" min="1" max="100" step="10" value="55"/>
<!-- max 允许的最大值； min 允许的最小值； step 规定合法的数字间隔； value 规定的默认值-->

Date Pickers	提供多个选取日期和时间的新输入类型	
<input type="date"/>
<!-- type值可以为date(选取日/月/年），month(月/年), week（周/年）， time(小时/分钟），
 datetime（时间/日/月/年（utc））， datetime-local(时间/日/月/年（本地时间))-->

url	url的输入域，在提交表单的时候，会自动验证url的值	
Homepage:<input type="email"  name="user_email"/>
 
search	搜索与，显示为常规的文本域	
<input type="search">


 （2）自定义数据属性 data-

作用： 为元素提供与渲染无关的信息，或者提供语义信息

用法：

<div id="myDiv" data-myId="123" data-name="liu"></div>  //html中使用

//js中调用
var myDiv=document.getElementById('myDiv');
var myId= myDiv.dataset.myId; //'123'，使用dataset属性访问自定义属性的值
var name= myDiv.dataset.name; //'liu'
 

2，css3部分

（1）css 变量

作用：为整个文档中重复使用的特定值。项目大了之后，方便统一修改

用法：使用自定义属性设置变量（--自定义属性名），使用特定的val()来访问 val(--自定义属性名）

https://developer.mozilla.org/zh-CN/docs/Web/CSS/Using_CSS_variables

 	声明	使用
全局变量	
//声明全局变量
:root{
   --global-color: #666;
}
//使用全局变量
.demo{
    color: var(--global-color);
}
局部变量	
//声明局部变量
element{
    --main-bg-color:red;
}
//使用局部变量
element{
    background-color: var(--main-bg-color);
}
 （2）：root

作用：伪类匹配文档树的根节点。对html来说，相当于<html>, 除了比<html>优先级高。

用法：一般用于声明全局css变量。

 https://developer.mozilla.org/zh-CN/docs/Web/CSS/:root

（3）filter过滤器

https://developer.mozilla.org/zh-CN/docs/Web/CSS/filter

作用：提供图像特效（模糊，锐化，元素变色），通常用于调整图片，背景和边界的渲染。

用法：

//预定义的函数
filter : blur(5px);
filter : grayscale(80%);

//svg滤镜
filte ： url(svg-url#element-id);
 

demo地址：

https://codepen.io/lunaliu/pen/RBoPYO

 