title: DOM事件
speaker: lizhiyuan
url:
theme:colors 
transition: rollIn
files:/css/style.css,/js/demo.js,/js/highlight/styles/github.css

[slide]
# 事件
## 演讲者：李志远

[slide] {:.flexbox.vleft}
##事件入门
1. 事件是什么
2. 事件有哪些类型
3. 事件如何去用
4. 事件的event对象
5. 事件默认行为
6. 常用事件


[slide] {:.flexbox.vleft}
##什么是事件?
事件是浏览器中的用户行为和客户端行为，它是浏览器规定好的行为
用户可以触发事件，浏览器再根据事件类型执行某些默认的操作,比如说点击
链接的时候跳转到某个页面上去，比如说点击提交的时候，跳转到某个页面上去.

用户触发事件------>浏览器监听到事件已经发生--------->执行默认的操作
---------->如果没有默认操作情况下，可指定事件发生后的操作(回调函数)


[slide] {:.flexbox.vleft}
##事件有哪些类型
事件有三种类型:鼠标事件、键盘事件、window事件
> 事件要知道：发生事件的元素、事件类型、事件函数

[slide] {:.flexbox.vleft}
##事件如何去用
```javascript
var a = document.querySelector('a');
    //事件元素.on + 事件类型 = 事件函数
    a.onclick = function(){
     alert(2);
     };
    //第三种通过使用addEventListener来添加事件
    var fun = function(){
        alert(3);
    }
    a.addEventListener('click',fun);
    //事件的第三个参数是指定是否进行冒泡和捕获的
    a.addEventListener('click',fn,false); //默认是冒泡
    a.addEventListener('click',fn,true) // 捕获
    //a.removeEventListener('click');错误的写法,移除事件
    //removeEventListener(box);错误的写法
    //removeEventListener(a,'click');错误的写法
    a.removeEventListener('click',fun);
    //当你不需要清除掉的时候，使用匿名函数，当你需要清除掉的时候，给函数命名
```

[slide] {:.flexbox.vleft}
##事件的event对象
* 当触发某个事件的时候，会产生一个事件对象，这个对象包含着所有与事件相关的信息
  包括导致事件的元素、时间的类型以及其它与特定事件相关的信息。
  事件对象，我们一般称作为<code>event</code>对象，这个对象是浏览器通过函数把这个对象作为参数传递进来的。
```html
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title>事件里面的event对象</title>
</head>
<body>
<a href="#">我要出发事件</a>
</body>
</html>
<script>
    var a = document.querySelector('a');
    //创建一个函数,并且传递了两个参数,num1,num2,返回的是两个参数相加之和
    a.addEventListener('click',function(event){
        console.log(event);
    });
</script>
```

[slide] {:.flexbox.vleft}
##事件默认行为
```html
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title></title>
</head>
<body>
<a href="http://www.baidu.com">我要跳向百度</a>
<form action="/" method="post">
    <input type="checkbox" name="person" value="sex">
    <input type="checkbox" name="person" value="name">
    <input type="checkbox" name="person" value="age">
    <select>
        <option value="1">1</option>
        <option value="2">2</option>
    </select>
    <input type="submit" value="提交">
    <input type="reset" value="重置">
</form>
</body>
</html>
<script>
    document.querySelector('a').addEventListener('click',function(e){
        e.preventDefault();
        //location.href = 'http://www.baidu.com';
    })
    document.querySelector('form').addEventListener('click',function(e){
        e.preventDefault();
    })
    //人家不是默认行为
    document.querySelector('select').addEventListener('click',function(e){
        e.preventDefault();
    })
</script>
```

[slide] {:.flexbox.vleft}
##常用事件
###表单事件
- submit事件  提交表单事件触发
- reset事件    重置表单事件触发
- click事件	点击表单事件触发	
- change事件	改变表单内容事件触发
- focus事件（不冒泡） （IE和ES5支持冒泡的focusin） 输入指针放在表单上触发,获取焦点
- blur事件（不冒泡） （IE和ES5支持冒泡的focusout）	输入指针移出表单上触发，失去焦点
- input事件（ES5 textinput提供更方便的获取输入文字的方案）
 
[slide] {:.flexbox.vleft}
##常用事件
###window事件
- load事件   某个页面或图像被完成加载
- DOMContentLoaded事件 仅仅当页面的DOM信息加载完毕的时候
- readyStatechage事件
- unload事件  用户退出页面
- beforeunload事件 在用户提出界面之前
- resize事件  窗口或框架被调整尺寸
- scroll事件  窗口发生滚动的时候加载
 
[slide] {:.flexbox.vleft}
##常用事件
###鼠标事件
- click事件	单击事件
- dblclick事件 	双击事件
- mousemove  事件会在鼠标指针移动时发生
- mouseover事件（冒泡）鼠标移到某元素之上，父元素也会触发
- mouseout事件（冒泡） 鼠标从某元素移开，父元素也会触发
- mousedown事件 鼠标按钮被按下。
- mouseup事件 鼠标按键被松开。
- contextmenu事件  鼠标右键，很少用
- mouseenter事件（不冒泡） 对应over事件，只有当前元素会触发
- mouseleave事件（不冒泡） 对应out事件，只有当前元素会触发
- mousewheel事件（FF DOMMouseScroll事件、DOM3 wheel事件）
 
[slide] {:.flexbox.vleft}
##常用事件
###键盘事件
- keydown事件
- keyup事件
- keypress事件


