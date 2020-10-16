## 1. JavaScript输出

JavaScript可以可以通过不同的方式来输出数据

- 使用windows.alert()弹出警告框；
- 使用document.write();方法将内容写到HTML文档中；
- 使用innerHTML写入到html元素中；
- 使用consoel.log();写入到浏览器的控制台

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>JavaScript教程</title>
  </head>
  <body>
    <h1>JavaScript输出数据方法</h1>
    <p id="demo">我的第一个段落</p>
    <button type="button" onclick="changeHtml()">点击修改</button>
  </body>

  <script>
    window.alert("弹出警告框");  //弹出警告框
    document.write(Date());  //将时间写入到html文档中

    function changeHtml(){
      document.getElementById("demo").innerHTML="段落内容已修改";
    }

    console.log("这句话会输出到控制台");
  </script>
</html>
```



## 2. JavaScript语法

### 2.1 JavaScript字面量

- 数字（Number）字面量 可以是整数或者是小数，或者是科学计数(e)。
- 字符串（String）字面量 可以使用单引号或双引号
- 表达式字面量 用于计算
- 数组（Array）字面量 定义一个数组
- 对象（Object）字面量 定义一个对象
- 函数（Function）字面量 定义一个函数

### 2.2 JavaScript变量

JavaScript 使用关键字 var 来定义变量， 使用等号来为变量赋值。变量可以通过变量名访问。在指令式语言中，变量通常是可变的。字面量是一个恒定的值。

### 2.3 JavaScript运算符

| 类型                   | 实例          | 描述                   |
| ---------------------- | ------------- | ---------------------- |
| 赋值，算术和位运算符   | =  +  -  *  / | 在 JS 运算符中描述     |
| 条件，比较及逻辑运算符 | ==  != <  >   | 在 JS 比较运算符中描述 |

### 2.4 JavaScript数据类型

值类型（基本类型）：字符串(String )、数字(Number)、布尔(Boolean)、对空(Null)、未定义(Undefined)、Symbol。

引用数据类型：对象(Object)、数组(Arrary)、函数(Function)。

Symbol是ES6引入的一种新的原始数据类型，表示独一无二的值。

Symbol是一种特殊的、不可变的数据类型，可以作为对象属性的标识符使用，表示独一无二的值。Symbol对象是一个symbol primitive data type的隐式对象包装器。

```javascript
//定义Symbol值的方式
let symbolProp = Symbol();

var obj = {};
obj[symbolProp] = 'hello Symbol';

//或者
var obj = {
 [symbolProp] : 'hello Symbol';
}

//或者
var obj = {};
Object.defineProperty(obj,symbolProp,{value : 'hello Symbol'});
```



- Symbol()函数生成的值都是不一样的。

- `Symbol.for()`调用的时候所返回的Symbol值得作用域是整个代码库，是一个全局的变量，第一次调用的时候就会登记。
- `Symbol.for()`调用的时候会在全局环境中检索给定的key值是否存在，如果不存在的话才会新建一个值，而Symbol()不会，Symbol()每次返回的都是不同的值。
- 注:转载自<https://www.jb51.net/article/112660.htm>

```javascript
		document.write("</br>");
    var a=Symbol();
    var b=Symbol();
    document.writeln(a==b);
    document.write("</br>");

    var c=Symbol.for("unilumin");
    var d=Symbol.for("unilumin");
    document.writeln(c==d);
    document.write("&nbsp&nbsp");
    document.write(Symbol.keyFor(c));
    document.write("</br>");

    var e=Symbol("unilumin");
    var f=Symbol("unilumin");
    document.write(e==f);
    document.write("&nbsp&nbsp");
    document.write(Symbol.keyFor(e));
    document.write("</br>");
```



```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>JavaScript教程</title>
  </head>
  <body>
    <h1>JavaScript语法</h1>
    <p id="demo1">我的第一个段落</p>
    <button type="button" onclick="changeNum()">点击修改数据</button>
    <p id="demo2">我的第一个段落</p>
    <button type="button" onclick="changeString()">点击修改字符串</button>
    <p id="demo3">我的第一个段落</p>
    <button type="button" onclick="listArr()">点击遍历数组</button>
    <p id="demo4">我的第一个段落</p>
    <button type="button" onclick="listObject()">点击遍历对象</button>
    <p id="demo5">我的第一个段落</p>
    <input id="param1" type="text">输入第一个参数</input></br>
    <input id="param2" type="text">输入第二个参数</input></br>
    <button type="button" onclick="myFunction()">点击运行乘法函数</button>
  </body>

  <script>
    
    //修改数据
    //根据鼠标点击的次数来决定显示的内容
    var t; //记录点击按钮的次数
    t=1;
    function changeNum(){
      if(t%5==0){
        document.getElementById("demo1").innerHTML="乘法表达式："+5*8;
      }else if(t%4==0){
        document.getElementById("demo1").innerHTML="加法表达式："+(5+8);
      }else if(t%3==0){
        document.getElementById("demo1").innerHTML="小数："+3.14;
      }else if(t%2==0){
        document.getElementById("demo1").innerHTML="整数："+10010;
      }else{
        document.getElementById("demo1").innerHTML="科学计数："+123e5;
      }
      t++;
    }
		
    //改变显示的字符串内容
    function changeString(){
      document.getElementById("demo2").innerHTML='字符串';
    }

    //遍历数组的内容
    function listArr(){
      var arr=[0, 1, 2, 3, 4, 5, 6, 7, 8, 9];
      var str="";
      for(var i=0; i<arr.length; i++){
        str=str+"第"+i+"个数:"+arr[i]+"</br>";
      }
      document.getElementById("demo3").innerHTML=str;
    }

    //遍历对象的内容
    function listObject(){
      var obj={firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};
      var str="";
      str="name:"+obj.firstName+"&nbsp"+obj.lastName+"</br>"+"age:"+obj.age+"</br>"+"eyeColor:"+obj.eyeColor;
      document.getElementById("demo4").innerHTML=str;
    }

    //乘法函数
    function myFunction() { 
      var a=document.getElementById("param1").value;
      var b=document.getElementById("param2").value;
      document.getElementById("demo5").innerHTML="函数运行结果："+a*b;
    }

    document.write("</br>");
    var a=Symbol();
    var b=Symbol();
    document.writeln(a==b);
    document.write("</br>");

    var c=Symbol.for("unilumin");
    var d=Symbol.for("unilumin");
    document.writeln(c==d);
    document.write("&nbsp&nbsp");
    document.write(Symbol.keyFor(c));
    document.write("</br>");

    var e=Symbol("unilumin");
    var f=Symbol("unilumin");
    document.write(e==f);
    document.write("&nbsp&nbsp");
    document.write(Symbol.keyFor(e));
    document.write("</br>");
  </script>
</html>
```

#### Undefined和Null ####

Undefined这个值表示变量不含有值。

可以通过将变量的值设置为null来清空变量。

#### 声明变量类型 ####

声明变量时，可以使用关键字“new”来声明变量的类型。

**JavaScript 变量均为对象。当您声明一个变量时，就创建了一个新的对象。**

```javascript
var carname=new String;
var x=new Number;
var y=new Boolean;
var cars=new Array;
var person=new Object;
```



### 3 JavaScript 对象

JavaScript对象是变量的容器。

```javascript
var car={type:"Fiat", model:500, color:"white"};
```

定义JavaScript对象可以跨越很多行，换行和空格并不是必须的。

```javascript
var person = {
    firstName:"John",
    lastName:"Doe",
    age:50,
    eyeColor:"blue",
  //对象中包含的方法
  	fullName : function() 
		{
       return this.firstName + " " + this.lastName;
    }
};
```

#### 3.1 访问对象属性

```javascript
//方式1
person.lastname;

//方式2
person["lastname"];
```



#### 3.2 对象方法

对象 方法定义了一个函数，并作为对象的属性存储。

对象方法通过添加()作为函数进行调用。

```javascript
name=person.fullname();
```



#### 3.3 访问对象方法

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title> 
</head>
<body>

<p>创建和使用对象方法。</p>
<p>对象方法是一个函数定义,并作为一个属性值存储。</p>
<p id="demo1"></p>
<p id="demo2"></p>
<script>
var person = {
    firstName: "John",
    lastName : "Doe",
    id : 5566,
    fullName : function() 
	{
       return this.firstName + " " + this.lastName;
    }
};
document.getElementById("demo1").innerHTML = "不加括号输出函数表达式："  + person.fullName;
document.getElementById("demo2").innerHTML = "加括号输出函数执行结果："  +  person.fullName();
</script>

</body>
</html>
```



### 4 JavaScript函数

函数是由事件驱动的或者当页面被调用时执行的可重复使用的代码块。



**局部JavaScript变量**

在JavaScript函数内部声明的变量是局部变量，所以只能在函数内部访问它（该变量的作用域是局部的）。因此在不同的函数内部可以声明名称相同的变量，因为只有声明过该变量的函数才能识别出该变量。

**注：**只要函数运行完毕，本地变量就会被删除。



**全局JavaScript变量** 

在函数外部声明的变量是全局变量，网页上的所有脚本和函数都能访问该变量。



**JavaScript变量的生存周期**

- JavaScript变量的生命期从变量被声明的时间开始。
- 局部变量会在函数运行过后被删除。
- 全局变量会在页面关闭之后被删除。



**尚未声明的JavaScript变量分配值**

如果赋值给尚未声明的变量，则该变量将被自动作为window的一个属性。

例如：

```javascript
carname="Volvo";
```

该条语句将会声明window的一个属性carname。

非严格模式下给未声明变量赋值创建的全局变量，是全局对象的可配置属性，可以删除。

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>JavaScript函数</title>
    <script>
      function myFunction1() {
        alert("Hello World!");
      }

      function myFunction2(name, job) {
        alert("Welcome " + name + ", the " + job);
      }

      function myFunction3(a, b) {
        alert(a * b);
        return a * b;
      }

      //return 可以用来直接跳出函数
      function myFunction4() {
        var a=parseInt(document.getElementById("param1").value);
        var b=parseInt(document.getElementById("param2").value);
        if (a > b) {
            document.getElementById("demo5").innerHTML="不满足条件，函数跳出";
          return;
        }
        x = a + b;        
        document.getElementById("demo5").innerHTML="函数运行结果："+x;
      }
    </script>
  </head>

  <body>
    <button onclick="myFunction1()">调用不带参数的函数</button></br></br>
    <button onclick="myFunction2('Harry Potter','Wizard')">调用带参数的函数</button></br></br>
    <button onclick="myFunction3(5,8)">调用带返回值的函数</button></br>
    <p id="demo5">我的第一个段落</p>
    <input id="param1" type="text">输入第一个参数</input></br>
    <input id="param2" type="text">输入第二个参数</input></br>
    <button type="button" onclick="myFunction4()">点击运行函数</button>
  </body>
</html>
```



### 5 JavaScript作用域

**作用域是可访问变量，对象，函数的集合。**

在JavaScript中，对象和函数同样也是变量。

**JavaScript局部作用域**

变量在函数内声明，变量为局部作用域。

局部变量：只能在函数内部访问。

**JavaScript全局变量**

变量在函数外定义，即为全局变量。

全局变量有**全局作用域**：网页中所有脚本和函数均可使用。

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>JavaScript语法</title>
  </head>
  <body>
    <p>局部变量在声明的函数外不可以访问。</p>
    <p id="demo1"></p></br>
    <p>全局变量在任何脚本和函数内均可访问。</p>
    <p id="demo2"></p></body><br>
    <p>如果你的变量没有声明，它将自动成为全局变量：</p>
    <p id="demo3"></p>
  </body>

  <script>
    //JavaScript局部变量
    myFunction1();
    function myFunction1() {
      var carName = "Volvo";
    }
    //因为在函数内生命的额变量为局部变量只在函数内部起作用，此处carname的类型应为undefined。
    document.getElementById("demo1").innerHTML =
      "carName 的类型是：" + typeof carName;

    //JavaScript全局变量
    var carName1 = "Volvo";
    myFunction2();
    function myFunction2() {
      document.getElementById("demo2").innerHTML = "我可以显示 " + carName1;
    }

    //未声明的变量自动转变为全局变量
    myFunction3();
    document.getElementById("demo3").innerHTML =	"我可以显示 " + carName2;
    function myFunction3() 
    {
        carName2 = "Volvo";
    }
  </script>
</html>
```

**JavaScript变量生命周期**

JavaScript变量生命周期在它生命时初始化。

局部变量在函数执行完毕后销毁。

全局变量在页面关闭后销毁。

**函数参数**

函数参数只在函数内起作用，是局部变量。

**HTML中的全局变量**

在HTML中，全局变量是window对象：所有数据变量都属于window对象。

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>JavaScript语法</title>
  </head>
  <body>
    <p>局部变量在声明的函数外不可以访问。</p>
    <p id="demo1"></p></br>
    <p>全局变量在任何脚本和函数内均可访问。</p>
    <p id="demo2"></p></body><br>
    <p>如果你的变量没有声明，它将自动成为全局变量：</p>
    <p id="demo3"></p>
  </body>

  <script>
    //JavaScript局部变量
    myFunction1();
    function myFunction1() {
      var carName = "Volvo";
    }
    //因为在函数内生命的额变量为局部变量只在函数内部起作用，此处carname的类型应为undefined。
    document.getElementById("demo1").innerHTML =
      "carName 的类型是：" + typeof carName;

    //JavaScript全局变量
    var carName1 = "Volvo";
    myFunction2();
    function myFunction2() {
      document.getElementById("demo2").innerHTML = "我可以显示 " + carName1;
    }

    //未声明的变量自动转变为全局变量
    myFunction3();
    document.getElementById("demo3").innerHTML =	"我可以显示 " + carName2;
    function myFunction3() 
    {
        carName2 = "Volvo";
    }
  </script>
</html>
```



### 6 JavaScript事件

HTML事件是发生在HTML元素上的事情。当在HTML页面中使用JavaScript时，JavaScript可以触发这些事件。

#### 6.1 HTML事件

HTML事件可以是浏览器行为，也可以是用户行为。

以下是HTML事件的实例：

- HTML页面完成加载
- HTML input字段改变时
- HTML按钮被点击

在事件触发时JavaScript可以执行一些代码。

HTML元素中可以添加事件属性，使用JavaScript代码来添加HTML元素。

```html
<!DOCTYPE html>
<html>
<head> 
<meta charset="utf-8"> 
<title>JavaScript事件</title> 
</head>
<body>
  <button onclick="getElementById('demo').innerHTML=Date()">现在的时间是?</button>
  <p id="demo"></p>
  <!--代码将修改自身的内容-->
  <button onclick="this.innerHTML=Date()">现在的时间是?</button>
</body>
</html>
```



#### 6.2 常见的HTML事件

| 事件        | 描述                         |
| :---------- | :--------------------------- |
| onchange    | HTML元素改变                 |
| onclick     | 用户点击html元素             |
| onmouseover | 用户在一个HTML元素上移动鼠标 |
| onmouseout  | 用户从一个HTML元素上移开鼠标 |
| onkeydown   | 用户按下键盘按键             |
| onload      | 浏览器已完成页面的加载       |

更多事件点击：[HTML DOM 事件](https://www.runoob.com/jsref/dom-obj-event.html)



### 7 JavaScript字符串

JavaScript字符串用于存储和处理文本。

字符串可以是插入到引号中的任何字符，可以使用单引号或双引号。

**在字符串中可以使用转义字符转义的特殊字符：**

| 代码 | 输出        |
| ---- | ----------- |
| \\'  | 单引号      |
| \\"  | 双引号      |
| \\\  | 反斜杠      |
| \\n  | 换行        |
| \\r  | 回车        |
| \\t  | tab(制表符) |
| \\b  | 退格符      |
| \\f  | 换页符      |

**字符串可以是对象**

创建字符串：`var firstName="John"`

创建字符串对象：`var firstName=new String("John")`

**注：**创建String类型的对象，会拖慢执行速度，并可能产生其他副作用。



可以通过使用索引位置来访问字符串中的每一个字符。

```html
<script>
    var carname = "Volvo XC60";
    alert(carname[0]);
    alert(carname[5]);
</script>
```



**字符串属性**：

| 属性        | 描述                       |
| ----------- | -------------------------- |
| constructor | 返回创建字符串属性的函数   |
| length      | 返回字符串的长度           |
| prototype   | 允许您向对象添加属性和方法 |



**字符串方法：**

| 方法                | 描述                                                         |
| :------------------ | :----------------------------------------------------------- |
| charAt()            | 返回指定索引位置的字符                                       |
| charCodeAt()        | 返回指定索引位置字符的 Unicode 值                            |
| concat()            | 连接两个或多个字符串，返回连接后的字符串                     |
| fromCharCode()      | 将 Unicode 转换为字符串                                      |
| indexOf()           | 返回字符串中检索指定字符第一次出现的位置                     |
| lastIndexOf()       | 返回字符串中检索指定字符最后一次出现的位置                   |
| localeCompare()     | 用本地特定的顺序来比较两个字符串                             |
| match()             | 找到一个或多个正则表达式的匹配                               |
| replace()           | 替换与正则表达式匹配的子串                                   |
| search()            | 检索与正则表达式相匹配的值                                   |
| slice()             | 提取字符串的片断，并在新的字符串中返回被提取的部分           |
| split()             | 把字符串分割为子字符串数组                                   |
| substr()            | 从起始索引号提取字符串中指定数目的字符                       |
| substring()         | 提取字符串中两个指定的索引号之间的字符                       |
| toLocaleLowerCase() | 根据主机的语言环境把字符串转换为小写，只有几种语言（如土耳其语）具有地方特有的大小写映射 |
| toLocaleUpperCase() | 根据主机的语言环境把字符串转换为大写，只有几种语言（如土耳其语）具有地方特有的大小写映射 |
| toLowerCase()       | 把字符串转换为小写                                           |
| toString()          | 返回字符串对象值                                             |
| toUpperCase()       | 把字符串转换为大写                                           |
| trim()              | 移除字符串首尾空白                                           |
| valueOf()           | 返回某个字符串对象的原始值                                   |

更多方法实例可以参见：[JavaScript String 对象](https://www.runoob.com/jsref/jsref-obj-string.html)。



### 8 JavaScript比较和逻辑运算符

**比较运算符**

| 运算符 | 描述       |
| ------ | ---------- |
| ==     | 等于       |
| ===    | 绝对等于   |
| !=     | 不等于     |
| !==    | 不绝对等于 |
| >      | 大于       |
| <      | 小于       |
| >=     | 大于或等于 |
| <=     | 小于或等于 |



**逻辑运算符**

| 运算符 | 描述 |
| ------ | ---- |
| &&     | and  |
| \|\|   | or   |
| !      | not  |



**条件运算符**

```javascript
voteable=(age<18)?"年龄太小":"年龄已达到";
//age=20 则voteable="年龄已达到"
```



### 9. JavaScript基本语句

#### 9.1 if...else语句

```javascript
if (time<10)
{
    document.write("<b>早上好</b>");
}
else if (time>=10 && time<20)
{
    document.write("<b>今天好</b>");
}
else
{
    document.write("<b>晚上好!</b>");
}
```



#### 9.2 switch语句

```javascript
var d=new Date().getDay(); 
switch (d) 
{ 
  case 0:x="今天是星期日"; 
  break; 
  case 1:x="今天是星期一"; 
  	break; 
  case 2:x="今天是星期二"; 
  	break; 
  case 3:x="今天是星期三"; 
  	break; 
  case 4:x="今天是星期四"; 
  	break; 
  case 5:x="今天是星期五"; 
 		break; 
  case 6:x="今天是星期六"; 
 	  break; 
  default:
    x="Wrong";
}
```



#### 9.3 JavaScript循环

**for循环**

```javascript
for (var i=0; i<5; i++)
{
      x=x + "该数字为 " + i + "<br>";
}
```



**for in 循环**：常用来遍历对象的属性

```javascript
for (var i=0; i<5; i++)
{
      x=x + "该数字为 " + i + "<br>";
}
```



**while循环**

```javascript
while (i<5)
{
    x=x + "The number is " + i + "<br>";
    i++;
}
```



**do while循环**：该循环至少会执行一次

```javascript
while (i<5)
{
    x=x + "The number is " + i + "<br>";
    i++;
}
```



#### 9.4 continue和break语句

**break:**break语句用于跳出循环。break语句跳出循环后，会继续执行该循环之后的代码。

```javascript
for (i=0;i<10;i++)
{
    if (i==3)
    {
        break;
    }
    x=x + "The number is " + i + "<br>";
}
```



**continue:**语句中断了循环中的迭代；用于跳过本次循环。

```javascript
for (i=0;i<=10;i++)
{
    if (i==3) continue;
    x=x + "The number is " + i + "<br>";
}
```

**注：**

continue 语句（带有或不带标签引用）只能用在循环中。

break 语句（不带标签引用），只能用在循环或 switch 中。

通过标签引用，break 语句可用于跳出任何 JavaScript 代码块

```javascript
cars=["BMW","Volvo","Saab","Ford"];
list: 
{
    document.write(cars[0] + "<br>"); 
    document.write(cars[1] + "<br>"); 
    document.write(cars[2] + "<br>"); 
    break list;
    document.write(cars[3] + "<br>"); 
    document.write(cars[4] + "<br>"); 
    document.write(cars[5] + "<br>"); 
}
```



#### 9.5 JavaScript typeof,null和undefined

**typrof 操作符:**可以使用typeof用来检测变量的类型。

```javascript
typeof "John"                // 返回 string
typeof 3.14                  // 返回 number
typeof false                 // 返回 boolean
typeof [1,2,3,4]             // 返回 object
typeof {name:'John', age:34} // 返回 object
typeof null									 //返回object
```



**null:**表示什么都没有，是一个只有一个值的特殊类型。表示一个空对象的引用。

```javascript
var person = null;           // 值为 null(空), 但类型为对象
```



**undefined:**在JavaScript中是一个没有设置值的变量。用typeof来判断类型是会返回undifined。

可以通过设置变量值为undifined的方式清空变量的值。

```javascript
person = undefined;          // 值为 undefined, 类型是undefined
```



**undefined和null的区别：**undefined和null的值相等但是类型并不相等。

```javascript
typeof undefined             // undefined
typeof null                  // object
null === undefined           // false
null == undefined            // true
```



### 10 JavaScript类型转换

#### 10.1 JavaScript数据类型

1. 六种不同的数据类型
   - string
   - number
   - boolean
   - object
   - function
   - symbol
2. 三种对象类型
   - Object
   - Date
   - Array
3. 两个不包含任何值的数据类型
   - null
   - undifined

#### 10.2 typeod操作符

可以使用typeof操作符查看变量的数据类型。

```javascript
typeof "John"                 // 返回 string
typeof 3.14                   // 返回 number
typeof NaN                    // 返回 number
typeof false                  // 返回 boolean
typeof [1,2,3,4]              // 返回 object
typeof {name:'John', age:34}  // 返回 object
typeof new Date()             // 返回 object
typeof function () {}         // 返回 function
typeof myCar                  // 返回 undefined (如果 myCar 没有声明)
typeof null                   // 返回 object
```

**注：**

- NaN 的数据类型是 number
- 数组(Array)的数据类型是 object
- 日期(Date)的数据类型为 object
- null 的数据类型是 object
- 未定义变量的数据类型为 undefined

如果对象是 JavaScript Array 或 JavaScript Date ，我们就无法通过 **typeof** 来判断他们的类型，因为都是 返回 object。



#### 10.3 construct属性

construct属性返回所有JavaScript变量的构造函数。

```html
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
</head>
<body>
<p> constructor 属性返回变量或对象的构造函数。</p>
<p id="demo"></p>
<script>
document.getElementById("demo").innerHTML = 
    "john".constructor + "<br>" +
    (3.14).constructor + "<br>" +
    false.constructor + "<br>" +
    [1,2,3,4].constructor + "<br>" +
    {name:'john', age:34}.constructor + "<br>" +
    new Date().constructor + "<br>" +
    function () {}.constructor;
</script>
</body>
</html>
```



使用construct属性判断对象是否为数组。

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
</head>
<body>
<p>判断是否为数组。</p>
<p id="demo"></p>
<script>
var fruits = ["Banana", "Orange", "Apple", "Mango"];
document.getElementById("demo").innerHTML = isArray(fruits);
function isArray(myArray) {
    return myArray.constructor.toString().indexOf("Array") > -1;
}
</script>
</body>
</html>
```



使用construct属性判断对象是否为日期。

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
</head>
<body>
<p>判断是否为日期。</p>
<p id="demo"></p>
<script>
var myDate = new Date();
document.getElementById("demo").innerHTML = isDate(myDate);
function isDate(myDate) {
    return myDate.constructor.toString().indexOf("Date") > -1;
}
</script>
</body>
</html>
```



#### 10.4 JavaScript类型转换

JavaScript变量可以转换为新变量或其他数据类型：

- 通过使用JavaScript函数。
- 通过JavaScript自身自动转换



**将数字转化为字符串：**

全局方法String()可以将数字转换为字符串。

该方法可以用于任何类型的数字，字母，变量，表达式。

```javascript
var x=123;
typeof(x);  //输出结果number
typeof(String(123));  //输出String
typeof(String(100 + 23));  //输出String
```



Nubmber方法toString()也有同样的效果。

```javascript
x.toString();
(123).toString();
(100 + 23).toString();
```



**将布尔值转换为字符串：**

全局方法 **String()** 可以将布尔值转换为字符串。

```javascript
String(false)     // 返回 "false"
String(true)     // 返回 "true"
```

Boolean 方法 **toString()** 也有相同的效果。

```javascript
false.toString()   // 返回 "false"
true.toString()   // 返回 "true"
```



**将日期转换为字符串：**

```javascript
Date() 返回字符串。
Date()   // 返回 Thu Jul 17 2014 15:38:19 GMT+0200 (W. Europe Daylight Time)
//全局方法 String() 可以将日期对象转换为字符串。
String(new Date())   // 返回 Thu Jul 17 2014 15:38:19 GMT+0200 (W. Europe Daylight Time)
//Date 方法 toString() 也有相同的效果。
obj = new Date()
obj.toString()  // 返回 Thu Jul 17 2014 15:38:19 GMT+0200 (W. Europe Daylight Time)
```



