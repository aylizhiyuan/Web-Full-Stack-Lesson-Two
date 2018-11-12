title: DOM--文档篇
speaker: lizhiyuan
url:
theme:colors 
transition: rollIn
files:/css/style.css,/js/demo.js,/js/highlight/styles/monnokai_sublime.css

[slide]
# DOM--文档篇
## 演讲者：李志远

[slide] {:.flexbox.vleft}
##DOM的概念
<iframe  src="http://baike.baidu.com/link?url=WevZMx-fe-2hAZXC-puhEVGYd7ePkg1ZUhJcWsyKylv1-ydncOPwzZUqK_H2IRKE8bUnwSAAU8ck93ROVRgMmK"></iframe>

[slide] {:.flexbox.vleft}
##DOM的学习顺序
document对象的学习，分为<b>文档类型</b>和<b>位置类型</b>
我们今天要学习的就是<b>文档类型</b>

1. ***DOM的查找***--首先定位到文档当中的节点
(就像CSS一样，先要找到选择器，这里，先找到要操作的元素)

2. ***DOM的遍历***--可以选择性的在当前的节点上继续定位
> 就像给了我们第二次选择的机会一样，第一次没成功不用修改我们就可以继续寻找

3. ***DOM的操作***--通过JS来达到修改HTML属性和内容的目的

4. ***DOM的操作***--删除、添加、替换HTML节点

[slide] {:.flexbox.vleft}
##DOM的查找
```html
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title></title>
</head>
<body>
<div id="a">我是通过ID选择器选择的节点</div>
<div class="b">我是通过CLASS选择器选择的节点</div>
<!--<div class="b">我是第二个通过class选择器选择的节点</div>
<div class="b">我是第三个通过class选择器选择的节点</div>-->
<p>我是通过标签选择的节点</p>
<p>我是第二个通过标签选择的节点</p>
<p>我是第三个通过标签选择的节点</p>
<ul>
    <li>1</li>
    <li>2</li>
    <li>3</li>
    <li>4</li>
</ul>
<input type="text" name="username">
<input type="text" name="password">
<input type="submit" value="提交">
<input type="reset" value="重置">
</body>
</html>
<script>
    //通过ID定位元素的
    var ele = document.getElementById('a');
    //console.log(ele.innerHTML);
    //通过class定位元素的
    var ele = document.getElementsByClassName('b')[0];
    console.log(ele.innerHTML);
    //通过标签来定位元素
    var ele  = document.getElementsByTagName('p')[0];
    //console.log(ele.innerHTML);
    //通过name值来定位元素的
    var ele = document.getElementsByName('username')[0];
    //console.log(ele.outerHTML);
    //通过CSS的选择器来定位元素
    var ele = document.querySelector('input');
    var ele = document.querySelectorAll('input');
    console.log(ele);
    //console.log(ele);
    //获取集合当中某一个具体的元素
    //***************************数组的下标是从0开始的
    //一定要记得给元素集合加下标
    document.getElementsByTagName('a')[1];
</script>
```

[slide] {:.flexbox.vleft}
##DOM的遍历
```html
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title>在DOM节点中继续遍历</title>
</head>
<body>
<div class="prev">我是相邻的上一个</div>
<ul>
    <li>HTML5</li>
    <li>css3</li>
    <li>javascript</li>
    <li>php</li>
</ul>
<!--df asdf-->
<div class="next" data-toggle="red">我是相邻的下一个</div>
</body>
</html>
<script>
    var ul = document.querySelector('ul');

    var li = document.querySelectorAll('li');
    //获取到UL的父节点,上级节点body
    var ulParent = ul.parentNode;
    //获取body的父节点，上级节点html
    //上层节点最高级别是document
    //alert(ulparent.parentNode.parentNode.parentNode);


    //获取所有的子节点
    var len = li.length - 1;
    var ulChild = ul.children[len];
    console.log(ulChild);

    //相邻的上一个、下一个
    var prev = ul.previousElementSibling;
    var next = ul.nextElementSibling;
    console.log(prev);

    //所有的元素都有三个节点属性:1.节点名称，2.节点属性,3.节点类型
    ul.nodeName;
    ul.nodeType;
    ul.nodeValue;
</script>
```

[slide] {:.flexbox.vleft}
##DOM的操作--修改属性和内容
```html
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title>修改DOM节点的属性和内容</title>
    <style>
        section {
            width:100px;
            height:100px;
            margin:10px auto;
            background:red;
        }
    </style>
</head>
<body>
<form action="/login.php" method="post">
    <input type="text" name="username">
    <input type="text" name="password">
    <input type="submit" value="提交">
</form>
<section><p>我的内容</p></section>
</body>
</html>
<script>
    var form = document.querySelector('form');
    //第一种方法,修改DOM节点的属性
    // .属性值 的方式来修改
    form.action = '/index.php';
    form.name = 'form';
    form.title = 'form';

    //第二种方法 getattribute,setattribute方法来获取和修改属性值
    //alert(form.getAttribute('action'));
    form.setAttribute('action','/index.php');
    //hasattribute是用来判断某个属性是否存在
    //removeattribute是用来删除某个属性的
    form.hasAttribute('action');
    form.removeAttribute('action');

    //第三种方法attribute对象的方法
    form.attribute[0];

    //如果你要得到非行内的属性，就必须要用getComputedStyle函数
    //getComputedStyle(element,null)[attr]
    var sec = document.querySelector('section');
    alert(getComputedStyle(sec)['width']);

    //sec.innerHTML = '我又修改了我的内容';
    //innerHTML只包含了内容，outerHTML包含了内容和元素本身,textContent不包含HTML标签，仅仅是文本内容
    alert(sec.innerHTML);
    alert(sec.outerHTML);
    alert(sec.textContent);
</script>
```

[slide] {:.flexbox.vleft}
##DOM的操作--添加、删除、替换节点
```html
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title>添加、移除、替换</title>
</head>
<body>
<ul>
    <li>HTML5</li>
    <li>CSS3</li>
    <li>JavaScript</li>
    <li>PHP</li>
    <li>python</li>
</ul>
</body>
</html>
<script>
    var ul = document.getElementsByTagName('ul')[0];
    var newli = document.createElement('li');
    var textnode = document.createTextNode('angularjs');
    newli.appendChild(textnode);
    /*插入到第一个前面*/
    ul.insertBefore(newli,ul.childNodes[1]);
    /*将新插入的节点删除掉*/
    ul.removeChild(newli);
    /*替换掉*/
    ul.replaceChild(newli,ul.childNodes[1]);
    ul.insertAdjacentText('beforeBegin', '外面的前面')
    ul.insertAdjacentHTML('afterBegin', '<li>里面的前面</li>')
    ul.insertAdjacentHTML('beforeEnd', '<li>里面的后面</li>')
    ul.insertAdjacentText('afterEnd', '外面的后面')
</script>
```

