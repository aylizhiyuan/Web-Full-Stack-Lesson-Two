title: 综合练习--tab切换
speaker: lizhiyuan
url:
theme:colors 
transition: rollIn
files:/css/style.css,/js/demo.js,/js/highlight/styles/monnokai_sublime.css

[slide]
# 综合练习--tab切换
## 演讲者：李志远

[slide] {:.flexbox.vleft}
##综合练习--tab切换
###HTML部分

````html

<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
    <title>简易选项卡</title>
</head>
<body>
<div id="outer">
    <ul id="tab">
        <li class="current">第一课</li>
        <li>第二课</li>
        <li>第三课</li>
    </ul>
    <div id="content">
        <ul style="display:block;">
            <li>网页特效原理分析</li>
            <li>响应用户操作</li>
            <li>提示框效果</li>
            <li>事件驱动</li>
            <li>元素属性操作</li>
            <li>动手编写第一个JS特效</li>
            <li>引入函数</li>
            <li>网页换肤效果</li>
            <li>展开/收缩播放列表效果</li>
        </ul>
        <ul>
            <li>改变网页背景颜色</li>
            <li>函数传参</li>
            <li>高重用性函数的编写</li>
            <li>126邮箱全选效果</li>
            <li>循环及遍历操作</li>
            <li>调试器的简单使用</li>
            <li>典型循环的构成</li>
            <li>for循环配合if判断</li>
            <li>className的使用</li>
            <li>innerHTML的使用</li>
            <li>戛纳印象效果</li>
            <li>数组</li>
            <li>字符串连接</li>
        </ul>
        <ul>
            <li>JavaScript组成：ECMAScript、DOM、BOM，JavaScript兼容性来源</li>
            <li>JavaScript出现的位置、优缺点</li>
            <li>变量、类型、typeof、数据类型转换、变量作用域</li>
            <li>闭包：什么是闭包、简单应用、闭包缺点</li>
            <li>运算符：算术、赋值、关系、逻辑、其他运算符</li>
            <li>程序流程控制：判断、循环、跳出</li>
            <li>命名规范：命名规范及必要性、匈牙利命名法</li>
            <li>函数详解：函数构成、调用、事件、传参数、可变参、返回值</li>
            <li>定时器的使用：setInterval、setTimeout</li>
            <li>定时器应用：站长站导航效果</li>
            <li>定时器应用：自动播放的选项卡</li>
            <li>定时器应用：数码时钟</li>
            <li>程序调试方法</li>
        </ul>
    </div>
</div>
</body>
</html>
````

[slide] {:.flexbox.vleft}
##综合练习--tab切换
###CSS部分

```css
body,ul,li{margin:0;padding:0;}
body{font:12px/1.5 Tahoma;}
#outer{width:450px;margin:10px auto;}
#tab{overflow:hidden;zoom:1;background:#000;border:1px solid #000;}
#tab li{float:left;color:#fff;height:30px;cursor:pointer;line-height:30px;list-style-type:none;padding:0 20px;}
#tab li.current{color:#000;background:#ccc;}
#content{border:1px solid #000;border-top-width:0;}
#content ul{line-height:25px;display:none;margin:0 30px;padding:10px 0;}
```

[slide] {:.flexbox.vleft}
##综合练习--tab切换
###javascript部分

```javascript
window.onload = function ()
        {
            var oLi = document.getElementById("tab").getElementsByTagName("li");
            var oUl = document.getElementById("content").getElementsByTagName("ul");

            for(var i = 0; i < oLi.length; i++)
            {
                //记录下下标
                //每一个li元素都添加一个属性来记录当前的下标值
                oLi[i].index = i;
                oLi[i].onmouseover = function ()
                {
                    for(var n = 0; n < oLi.length; n++) oLi[n].className="";
                    this.className = "current";
                    for(var n = 0; n < oUl.length; n++) oUl[n].style.display = "none";
                    oUl[this.index].style.display = "block"
                }
            }
        }
```
[slide] {:.flexbox.vleft}
##综合练习--tab切换
###效果
<iframe src='/demos/tab.html'></iframe>
