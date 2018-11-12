title: javascript基本数据类型
speaker: lizhiyuan
url:
theme:colors 
transition: stick
files:/css/style.css,/js/demo.js,/js/highlight/styles/github.css
[slide]
#javascript数据类型 {:&.flexbox.vright}
##主讲人:李志远

[slide style="background-image:url('/img/03.jpg')"]
##javascript已经超越了很多语言
<iframe class="widder" src="//www.tiobe.com/tiobe-index/" frameborder="0"></iframe>


[slide style="background-image:url('/img/02.jpg')"]
##六大数据类型 
----
* Number {:&.rollIn}
* String
* Boolean
* Null
* Undefined
* Object

[slide] {:.flexbox.vleft}
##Number类型的创建
```html
<script>
/*我们的JS代码*/
    //number类型
    //在JS当中，声明一个变量，需要使用var关键字,var的作用就是为了开辟一块
    //存储内容的空间,这个空间的地址以名字方式记录
    //具体的格式:var + 变量名
    //1.在进行变量命名的时候，尽量的有意义
    //2.变量名区分大小写, 尽量采用驼峰式命名 liZhiYuan welcomeToMyHome
    //3.变量名用数字、字母、下划线组成,不要跟关键字冲突
    var num1 = 10;
    /*alert(typeof num1);*/
    var num2 = -10;
    /*alert(typeof num2);*/
    var num3 = 0.1;
    /*alert(typeof num3);*/
    var num4 = 0.000000000000001;
    //十六进制的数字写法
    var num5 = 0xff;
    /*alert(typeof num5);*/
    var num6 = 065;
    /*alert(typeof num6);*/
    //错误的类型
    //var num100 = 50%;
</script>
```

[slide] {:.flexbox.vleft}
##String类型的创建
```html
<script>
    //字符串类型string
    var str1 = '我是字符串';
    var str2 = "我也是字符串";
    //var str3 = <我是字符串>;
    //var str4 = {我是字符串};
    //var str5 = (我是字符串);
    //alert(typeof str5);
    //var str6 = [我是字符串];
    //alert(typeof str6);
    var str7 = "我是字符串'内的字符串'";
    var str8 = '我是字符串"内的字符串"';
    //alert( str8);
</script>
```


[slide] {:.flexbox.vleft}
##Boolean类型的创建
```html
<script>
        //布尔类型
        var bool1 = true;//为真
        var bool2 = false;//为假
        alert(typeof bool2);
        var bool3 = 1;
        //alert(typeof bool3);
        var bool4 = 0;
</script>
```

[slide] {:.flexbox.vleft}
##Null和Undefined
```html
<script>
            //未定义undefined
            var a;
            //null空的，没有内容的
            var b = null;
</script>
```
> 区别:<br>
undefined: 代表一切未知的事物，啥都没有，无法想象，代码也就更无法去处理了。<br>
null: 有那么一个概念，但没有东西。无中似有，有中还无。虽难以想象，但已经可以用代码来处理了。

[slide] {:.flexbox.vleft}
##Object类型的创建
```html
<script>
       var obj = {};
</script>
```
[slide]
##总结:创建数据类型的标准规则
----
<img src='/img/data.png'>




