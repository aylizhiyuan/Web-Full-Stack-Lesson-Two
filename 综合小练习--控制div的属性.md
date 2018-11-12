title: 综合练习--控制div的属性
speaker: lizhiyuan
url:
theme:colors 
transition: rollIn
files:/css/style.css,/js/demo.js,/js/highlight/styles/monnokai_sublime.css

[slide]
# 综合练习--控制div的属性
## 演讲者：李志远

[slide] {:.flexbox.vleft}
##综合练习--控制div的属性
###HTML部分

````html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
    <title>控制div属性</title>
</head>
<body>
<div id="outer">
    <input type="button" value="变宽" />
    <input type="button" value="变高" />
    <input type="button" value="变色" />
    <input type="button" value="隐藏" />
    <input type="button" value="重置" />
    <div id="div1"></div>
</div>
</body>
</html>
````

[slide] {:.flexbox.vleft}
##综合练习--控制div的属性
###CSS部分

```css
#outer{width:500px;margin:0 auto;padding:0;text-align:center;}
#div1{width:100px;height:100px;background:black;margin:10px auto;display:block;}
```

[slide] {:.flexbox.vleft}
##综合练习--控制div的属性
###javascript部分

```javascript
var changeStyle = function (elem, attr, value){
     elem.style[attr] = value
};
window.onload = function (){
    var oBtn = document.getElementsByTagName("input");
    var oDiv = document.getElementById("div1")
    var oAtt = ["width","height","background","display","display"];
    var oVal = ["200px","200px","red","none","block"];
    for (var i = 0; i < oBtn.length; i++){
        oBtn[i].index = i;
        oBtn[i].onclick = function (){
            //当检测到最后一个的时候，将它的默认的行内样式清空
            this.index == oBtn.length - 1 && (oDiv.style.cssText = "");
            changeStyle(oDiv, oAtt[this.index], oVal[this.index])
        }
    }
};
```
[slide] {:.flexbox.vleft}
##综合练习--控制div的属性
###效果
<iframe src='/demos/div.html'></iframe>

