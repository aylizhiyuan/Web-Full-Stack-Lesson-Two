title: DOM--位置篇
speaker: lizhiyuan
url:
theme:colors 
transition: rollIn
files:/css/style.css,/js/demo.js,/js/highlight/styles/github.css

[slide]
# DOM--位置篇
## 演讲者：李志远

[slide] {:.flexbox.vleft}
##获取窗口、页面、元素的大小和位置
1. 窗口的位置
2. 屏幕的大小
3. 可视区域的大小
4. 文档的大小
5. 滚动条的大小
6. 元素的大小
7. 元素相对于父元素的位置
8. 元素相对于文档的位置


[slide] {:.flexbox.vleft}
##窗口的位置
```javascript
//整个浏览器窗口的位置
    alert(screenLeft);
    alert(screenTop);
    //Firefox支持的
    alert(screenX);
    alert(screenY);
    //兼容写法
    var leftX = screenLeft ? screenLeft : screenX ;
    var topY = screenTop ? screenTop : screenY;
```

[slide] {:.flexbox.vleft}
##屏幕的大小
```javascript
     //屏幕的大小
     window.screen.width;
     window.screen.height;
```

[slide] {:.flexbox.vleft}
##可视区域的大小
```javascript
        //视图的大小
         window.innerWidth;
         window.innerHeight;
         document.documentElement.clientWidth;
         document.documentElement.clientHeight;
```

[slide] {:.flexbox.vleft}
##文档的大小
```javascript
         //文档的大小   
         document.documentElement.offsetWidth;
         document.documentElement.offsetHeight;
         document.body.clientWidth;
         document.body.clientHeight;
```

[slide] {:.flexbox.vleft}
##滚动条的大小
```javascript
         //滚动条的大小   
         document.documentElement.scrollTop;
         document.documentElement.scrollLeft;
         document.body.scrollTop;
         document.body.scrollLeft;
```

[slide] {:.flexbox.vleft}
##元素的大小
```javascript
//元素的大小   
            //先看看这个盒子的clientwidth,height
             var section = document.getElementsByTagName('section')[0];
             console.log(section.clientWidth);
             console.log(section.clientHeight);
             //在看看加上border的大小
             console.log(section.offsetWidth);
             console.log(section.offsetHeight);
             //如果出现了滚动条，本身元素出现了滚动条，那么要算上滚动条的大小
             console.log(section.scrollWidth);
             console.log(section.scrollHeight);
```

[slide] {:.flexbox.vleft}
##元素相对于父元素的位置
```javascript
var section = document.getElementsByTagName('section')[0];
    console.log(section.offsetLeft);
    console.log(section.offsetTop);
    //元素如果出现滚动条的话
    console.log(section.scrollLeft);
    console.log(section.scrollTop);
```

[slide] {:.flexbox.vleft}
##元素相对于文档的位置
```javascript
//js原生没有提供相对于文档的位置，需要自己去计算
//获取某一个元素到最外层顶点的位置
function offsetTop(element) {
    var top = element.offsetTop;
    var parent = element.offsetParent;
    while (parent != null) {
        top += parent.offsetTop;
        parent = parent.offsetParent;
    }
    return top;
}
```


[slide]
# 智游集团
## nodeJS培训课程