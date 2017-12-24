---
layout:     post
title:      对事件冒泡,正则表达式的理解
category: blog
description: 初学事件冒泡和正则时的笔记
---

<h2>在js中有一个专门的事件对象,来对事件进行操作:</h2>

event:当事件发生时,与事件有关的信息存储在一个临时的地方-event对象里面.供我们随时调用

event对象的方法:

clientX:鼠标距离页面可视区域左边的距离,相应的Y为上边的距离

事件流里的事件冒泡现象:

首先,试想冒泡是什么意思,在沸水里冒泡泡,物质从一个介质中提炼出来进入另一个介质,这就是冒泡现象;那么事件冒泡就是当一个元素接受到事件时,会把它接收的所有信息传给父级,一直到顶层window,这种现象为事件冒泡机制.

认识一下事件:

事件的存在并不受事件函数的影响,比如无论div元素是否绑定了onclick事件,当你点击div时,点击这个事件已经存在了,只是如果未绑定事件函数的话,什么也不会发生而已.

事件冒泡会解决很大一部分重复操作,但是有时候需要某个元素脱离事件流,不参与冒泡所以在要阻止的事件函数中添加event.cancelBubble=true;语句,cancelBubble意为取消冒泡.例:
```
oBtn.onclick=function(){
  var ev=ev||event; 这是为兼容性考虑
  ev.cancelBubble=true;  阻止oBtn点击事件的冒泡现象;
}
```
接下来学习另外一种绑定事件函数的方法:

首先我们掌握的绑定事件函数的方法为:`obj.onclick=function(){};`但当我们需要绑定多个函数为点击事件时就会出现问题
```
obj.onclick=function fn1(){};
obj.onclick=function fn2(){};
```
这样写,fn2会覆盖fn1,二者不能共存,所以出现第二种方法可以使多个函数共存,但是第二种绑定存在兼容性问题:

`ie:obj.attachEvent("on"+事件名称,事件函数)`

1.没有捕获

2.事件名称必须加"on"

3.事件函数的执行顺序:ie 678为倒序执行,即先执行写在下面的函数,ie9以后为正序.

4.this指向Window(即在使用this时,事件函数相当于绑定到了Window)

`w3c:obj.addEventListenner(事件名称,事件函数,是否捕获);`

1.有捕获   默认false为冒泡   true为捕获 

2.事件名称没有"on"

3事件顺序只有正序

4.this指向当前对象(正常)

例子:
```
function ok(obj,evname,fn){                           定义三个参数,接下来的函数中要用

  绑定事件函数存在兼容性问题,所以用if:

  if(obj.addEventListenner){ 
    obj.addEventListenner(evname,fn1,false);         w3c浏览器
    obj.addEventListenner(evname,fn2,false);
  }else{
    obj.attachEvent(     "on"+evname , function(){fn1.call(obj);  在该事件函数中添加这句解决this问题}   ); 在ie,由于this指向有问题,所以用call修正为obj
    obj.attachEvent(     "on"+evname , function(){fn2.call(obj);}                                       );
    };

}
```
如上,第二种绑定事件函数的方法可以使fn1和fn2共存,但执行顺序ie和w3c有所不同.

call方法为function函数的一种原生方法,就像数组里的push一样.
call意为调用函数:fn()==fn.call() 这两个是完全一样的,但call更为强大,使用call调用函数时可直接传参,其中第一个参数可以改变函数内部this的指向,从第二个参数开始就是原来的函数参数列表.如果第一个参数为null即空,则不改变this指向.

<h2>cookie的作用是存储数据,当用户访问网站时,将一些数据存储在用户电脑上.</h2>

1.不同浏览器cookie位置不一样

2.同一浏览器不同的网站有不同的cookie,甚至同一网站也存在多个cookie. 所以首先cookie存储是以域名进行区分的,其次每一个cookie可以单独设置名字.
通过document.cookie获取当前网站的cookie,得到的是字符串,包含当前网站所有的cookie.通过";"+"空格"串联起来.

3.一个域名下的cookie数目有限,并且每个cookie存放内容大小也有限,不同的浏览器对数目的限制不一样.

4.但若想永久存放cookie也是可以的,设置一个过期时间就好了,不设置的话cookie默认是临时存储,当浏览器关闭时就销毁

5.cookie的内容最好编码存放,因为像中文字符这种特殊字符会出现乱码.encodeURI编码,decodeURI解码

下面举实例:
```
function setCookie(key,value,t){            设置一个实现长期保存cookie的函数
    var oDate=new Date();              获取当前日期
    oDate.setDate(oDate.getDate()+t);       设置日期为当前日期+某个数字t(设定几天后失效)
   document.cookie=key+"="+value+";expire="+oDate.toGMTstring();     cookie数据采用json格式
}
```
  上述函数实现setCookie(key,value,t)就输出字符串key+"="+value+";expire="+oDate.toGMTstring(),并且在设定好的过期日期以后才失效.
```
function getCookie(key){               设置获取cookie的函数
    var arr1=document.cookie.split(";");     split和数组里是一样的用法,以";"分隔
    for(var i=0;i<arr1.length;i++){
        var arr2=arr1[i].split("=");       因为获取的时候会获取所有cookie,所以要分隔
        if(arr2[0]==key){
            return decodeURI(arr2[i]);   解码文字部分
        }
    }
}
```
下面是移除cookie的函数
```
function removeCookie(key){
    setCookie(key," ",-1);     小技巧,设置当前日期的-1天也就是昨天失效,自然就移除了cookie.
}
```

<h2>首先就正则两个字解释:顾名思义,正则可以理解为正确的规则.</h2>

先来复习一遍js中对字符串的操作
```
search()寻找字符串中某字符第一次出现的位置(下标),若找不到返回-1.
substring(a,b)不包含结束位置,ab指的是下标.获取a到b之间的字符.
charAt(a),根据下标找出字符串里的字符.注意search返回下标,而charAt返回字符.
split("-")在字符串中若有"-",则用"-"分割字符串,返回数组.
match(re)匹配 检索字符串,按照re的规则提取出来字符串,返回数组
replace(a,b)将a替换为b
```
正则表达式可以极大简化普通字符串操作(简化90%吧,不夸张的说)
正则表达式仅仅是一个计算机方便识别并操作字符串的式子,
RegExp是其大名,但是比较麻烦,比如
```
var str="abAd";
var re=new Reg Exp("a","i");     第一个参数即为正则表达式,第二个参数(即正则的选项)为忽略大小写,ignore
```
官方说法是js风格的正则,但是它有个小名更简单,以上可以简写为
```
var str="aijg";
var re=/a/i;
```
真的是超级简单,所以大家都是用小名.官方说法为perl风格.

除了直接写要找的字符外,正则还有一些转义(转变意义)字符更方便

\d  digital代表某个数字,  \D 大写就代表相反区间`[^0-9]`

[]表示在一个范围内取一个值例如`/1a2|1b2|1c2/`可以简写为`/1[abc]2/`

^在 [ ] 中代表排除,意为除此之外.-代表范围,0-9代表0到9的数字

\w word 字符`[a-z0-9_]`  \W大写代表相反`[^a-z0-9_]`

\s  即space 空白 代表空格,制表符等空的东西,  \S则恰恰相反,所有不空的东西

正则里的量词:{m,n}代表m到n个字符,不写m代表最多n个,不写n代表至少m个,只写m代表正好m个

例如`\d{m,n}`意为m到n个数字,+表示多个的意思

例如`/\d+/`,多个数字.相当于`\d{1,}`

`*`表示`{0,}`但不建议用, `?`等于`{0,1}`, ` \.`代表` . `(点)

^不在[]里代表行首,$代表行尾,例如`var re=str.repalce(/^\s+|\s+$/g,"");`替换字符串左右两边的空格为空(去掉行首尾空格)

`|`是或的意思`g`是global 全局匹配.