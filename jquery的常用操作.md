# jQuery 的基本操作

## 事件

-   js 中指的事件如: onclick onmouseenter onmouseleave onmouseup onmousedown 等...
-   jQuery 中指的事件如: click mouseenter mouseleave mouseup mousedown
-   在 js 中 obj.onclick = function(){ 事件处理 }
-   在 jq 中 \$(obj).click(function(){ 事件处理 })
-   原生 js 写法是调用属性 obj.onclick , jq 写法调用方法 obj.click()

## js 与 jq 入口函数的区别

-   执行时间
    -   window.onload 必须等到页面内包含图片的所有元素加载完毕后才能执行
    -   \$(document).ready()是 DOM 结构回执完毕后就执行,不必等到加载完毕.只加载 dom 框架,对打的图片需要时间这个不等
-   编写个数
    -   window.onload 不能同时编写多个 如果有多个 window.onload 方法 只会执行一个
    -   \$(document).ready()可以同时编写多个 并且都可以得到执行

## jQ 的基本选择器

|       符号        |                  说明                  |                 用法                 |           介绍           |
| :---------------: | :------------------------------------: | :----------------------------------: | :----------------------: |
|    \$('#demo')    |         选择 id 为 demo 的元素         |    \$('#demo').css('color','red')    | 设置颜色 color 为 red 色 |
|    \$('.demo')    |       选择 class 为 demo 的元素        |    \$('.demo').css('color','red')    | 设置颜色 color 为 red 色 |
|     \$('div')     |        选择所有的 div 标签元素         |    \$('.demo').css('color','red')    | 设置颜色 color 为 red 色 |
|     \$('\*')      |           选择所有的标签元素           |     \$('\*').css('color','red')      | 设置颜色 color 为 red 色 |
| \$('.demo.demo2') | 选择同时具有.demo 和 .demo2 的标签元素 | \$('.demo.demo2').css('color','red') | 设置颜色 color 为 red 色 |

### 层级选择器

| 符号 |    说明    |               用法                |           介绍           |
| :--: | :--------: | :-------------------------------: | :----------------------: |
| 空格 | 后代选择器 | \$('div span').css('color','red') | 设置颜色 color 为 red 色 |
|  >   | 子代选择器 | \$('div>span').css('color','red') | 设置颜色 color 为 red 色 |
|  +   | 紧邻选择器 | \$('div+span').css('color','red') | 设置颜色 color 为 red 色 |
|  ~   | 兄弟选择器 | \$('div~span').css('color','red') | 设置颜色 color 为 red 色 |
| 空格 | 后代选择器 | \$('div span').css('color','red') | 设置颜色 color 为 red 色 |

### 属性选择器

|            符号             |                     说明                      |                      用法                      |           介绍           |
| :-------------------------: | :-------------------------------------------: | :--------------------------------------------: | :----------------------: |
|        \$('a[href]')        |            具有 href 属性的 a 标签            |        \$('a[href]').css('color','red')        | 设置颜色 color 为 red 色 |
|    \$('a[href='baidu']')    |          href 属性为 baidu 的 a 标签          |    \$('a[href="baidu"]').css('color','red')    | 设置颜色 color 为 red 色 |
|   \$('a[href!='baidu']')    |         href 属性不为 baidu 的 a 标签         |   \$('a[href!="baidu"]').css('color','red')    | 设置颜色 color 为 red 色 |
|    \$('a[href[^='www']')    |         href 属性以 www 开头的 a 标签         |    \$('a[href^="www"]').css('color','red')     | 设置颜色 color 为 red 色 |
|     $('a[href$='cn']')      |         href 属性以'cn'结尾的 a 标签          |     $('a[href$="cn"]').css('color','red')      | 设置颜色 color 为 red 色 |
|     \$('a[href=*='i']')     |           href 属性包含'i'的 a 标签           |     \$('a[href=*="i"]').css('color','red')     | 设置颜色 color 为 red 色 |
| \$('a[href][title='内容']') | 具有 href 属性且 title 属性为 '内容'的 a 标签 | \$('a[href][title='内容']').css('color','red') | 设置颜色 color 为 red 色 |

### 基本筛选选择器

|    符号    |             说明             |               用法                |           介绍           |
| :--------: | :--------------------------: | :-------------------------------: | :----------------------: |
| :eq(index) |   匹配一个给定索引值的元素   | \$('li:eq(1)').css('color','red') | 设置颜色 color 为 red 色 |
| :gt(index) | 匹配所有大于给定索引值的元素 | \$('li:gt(1)').css('color','red') | 设置颜色 color 为 red 色 |
| :lt(index) | 匹配所有小于给定索引值的元素 | \$('li:gt(2)').css('color','red') | 设置颜色 color 为 red 色 |
|    :odd    |  匹配所有索引值为奇数的元素  |  \$('li:odd').css('color','red')  | 设置颜色 color 为 red 色 |
|   :even    |  匹配所有索引值为偶数的元素  |  \$('li:odd').css('color','red')  | 设置颜色 color 为 red 色 |
|   :first   |     获取匹配的第一个元素     | \$('li:first').css('color','red') | 设置颜色 color 为 red 色 |
|   :last    |    获取匹配的最后一个元素    | \$('li:last').css('color','red')  | 设置颜色 color 为 red 色 |

### 其他选择器

|      符号       |                 说明                 |           用法            | 介绍 |
| :-------------: | :----------------------------------: | :-----------------------: | :--: |
|     :empty      | 匹配所有不包含子元素或者文本的空元素 |      \$('li:empty')       |      |
| :contains(text) |        匹配包含给定文本的元素        | \$('li:contains('join')') |      |

## DOM 操作

-   样式操作 `.css()`
    -   获取样式
    -   设置单个属性样式
    -   设置多个属性样式
-   属性操作 `.attr()`
    -   获取属性 \$('img').attr('src') 获取 img 的 src 属性值
    -   设置属性 \$('img').attr({src:'text.jpg',alt:"sorry"})
    -   删除属性 removeAttr() \$('img').removeAttr('src')
-   html 代码/文本/值 可以取值,设值
-   html() $('p').html()   $('p').html('html 代码')
-   text() $('p').text()   $('p').text('text 代码')
-   value() $('input').value()   $('input').value('你好?明天')
-   prop() $('input').prop("checked")   $('input').prop('checked',false)

## 类名操作

-   addClass() 向被选元素添加一个或多个类
-   removeClass() 从被选元素删除一个或多个类
-   toggleClass() 对被选元素进项添加/删除
-   类的切换操作
-   hasClass() 判断被选元素是否存在类

## dom 筛选过滤/查找

-   eq(index)
-   find() 符合条件的后代节点
-   siblings() 除了自己意外的所有兄弟节点
-   children() 所有孩子节点
-   next() 下一个兄弟节点
-   nextAll() 后面的所有兄弟节点
-   nextUntil() 后面的兄弟节点 直到....
-   prev() 上一个兄弟节点
-   prevAll()
-   prevUntil()
-   parent() 父节点
-   parents() 所有父节点
-   parentsUntil() 所有父节点

## jQ 动画

-   隐藏(hide) / 显示(show)
    -   \$(selector).show(2000);
    -   \$(selector).show(slow); slow / normal / fast
    -   \$(selector).show(2000,function(){});
    -   \$(selector).show();
-   滑入滑出动画
    -   \$(selector).slideDowm(speed,callback);
    -   \$(selector).slideUp(speed,callback);
    -   \$(selector).slideToggle(speed,callback);
-   淡入淡出动画
    -   \$(selector).fadeIn(speed,callback);
    -   \$(selector).fadeOut(speed,callback);
    -   \$(selector).fadeToggle(speed,callback);
    -   \$(selector).fadeTo(speed,opacity); // 调节透明度
    -   **省略参数或者传入不合法的字符串,那么则使用默认值:400 毫秒**

### 自定义动画

-   \$(selector).animate(styles,speed,ease,callback)
    -   styles 要执行动画的 css 属性 (必选)
    -   speed 执行动画时常(可选)
    -   ease 运动函数 `swing` 和 `linear`
    -   callback 动画执行完后立即执行的回调函数(可选)
-   停止动画
    -   stop() 停止当前动画
    -   如果有多个动画同时作用于一个单位上面,那么就多个动画会进入排队,后一个动画的执行必须等前面的执行完毕
    -   stop(stopAll , goToEnd)
    -   stopAll 是否全部停止动画(停止队列所有动画),默认 false
    -   goToEnd 是否将停止的动画,停止在当前动画的最后一个状态

## 插入节点

-   append()
    -   参数: jq 对象 或 标签字符串 或 DOM 对象
    -   作用: 在被选元素内部从后面插入
    -   如果是页面中存在的元素,那么调用 append()后,会把这个元素放到相应的目标元素里面去,但是原来的元素就不存在了(剪切)
    -   如果是给多个目标追加元素,那么方法的内容会复制多份这个元素,然后追加到多个目标里面去
-   appendTo()
    -   作用: 把\$(selector)追加到 node 中去
    -   \$(selector).appendTo(node)
-   prepend()
    -   作用:在被选元素内部从前面追加内容或节点
-   after()
    -   作用:在被选元素之后,作为兄弟元素插入内容或节点
    -   \$(selector).after(node)
-   before()
    -   作用: 在被选元素之前,作为兄弟元素插入内容或节点
    -   \$(selector).before(node)
    -   **对于这些添加方法 node 可以是 jq 对象 或 标签字符串 或 DOM 对象**

## 清空元素

-   \$(selector).empty();
-   \$(selector).html("");
-   \$(selector).remove(); // 会把自己也删除

## 复制元素

-   \$(selector).clone()

## BOM 相关

-   height()
-   height(200)
-   width()
-   width(200)
-   **取值类型为 num 可以直接参与运算**

## 坐标值操作

-   offset()
    -   作用: 获取或设置元素相对于文档的位置
    -   \$(selector).offset()
    -   \$(selector).offset({left:100,top:150})
-   position()
    -   作用: 获取相对于其最近具有定位的父元素的位置
    -   \$(selector).position()
    -   注意: 只能获取 不能设置
-   scrollTop()
    -   作用:获取或者设置元素垂直方向滚动的位置
    -   \$(selector).scrollTop()
    -   \$(selector).scrollTop(100)

```js
// 宽度和高度的获取与设置
console.log($(obj).height()) // 获取元素的宽度与高度 不包含 padding border
$(obj).height(500)  // 设置元素的高度
console.log($(obj).height()) // 从新获取元素的宽度与高度 不包含 padding border
console.log($(obj).width()) // 获取元素的宽度与高度 不包含 padding border
$(obj).width(500)  // 设置元素的高度
console.log($(obj).width()) // 从新获取元素的宽度与高度 不包含 padding border

offset() 作用: 获取或设置元素相对文档的位置
$(selector).offset() // 获取位置
$(selector).offset({left:100,top:150}) // 设置位置
console.log("obj相对与文档的位置 left",$(obj).offset().left)
console.log("obj相对与文档的位置 top",$(obj).offset().top)
$(obj).offset({
    left:60,
    top:60
})

position 作用:获取相对于其最近的具有定位的父元素的位置
console.log('元素 position位置 left',$('元素').position().left)
console.log('元素 position位置 top',$('元素').position().top)

scrollLeft() 作用: 获取或者设置元素水平方向滚动的位置
$('.top').click(function(){
    console.log($(document.documentElement).scrollTop())
    $(document.documentElement).animate({
        scrollTop:0
    })
})
```

## on 方式绑定事件

-   target.on(type,[selector],[data],fn) 在选择元素上绑定事件处理函数
    -   target : 选择元素(jq 对象)
    -   type : 事件类型
    -   selectot : 一个选择器字符串,用来过滤选定的元素(target 后代),如果省略.则 target 所有后代元素都会触发事件
    -   data : 当一个事件被触发时要传递 event.data 给事件处理函数 (可以省略)
    -   fn: 该事件被处罚时执行的函数

## off 解绑事件

-   .off() 方法移除用.on() 绑定的事件处理程序
-   .off() 结束所有绑定的事件
-   .off('click') 解绑所有绑定的 click 事件 元素本身的事件不会被解绑
-   .off('click','xx')
-   .off('click','xx',fn)

## 事件对象 Event

-   event.data 传递给事件处理程序的额外数据
-   event.currentTarget 事件绑定的对象(事件源)和 this 相同
-   event.pageX 鼠标相对于文档左部边缘位置
-   event.target 实际触发事件的对象 不一定 === this
-   event.stopPropagetion() 阻止事件冒泡
-   event.preventDefault() 阻止默认行为
-   event.type 事件类型 如 click mouseover
-   event.which 鼠标的按键类型 左 1 中 2 右 3
-   event.keyCode 键盘按键代码

```js
$(obj).click(function(event) {
    console.log(event);
    console.log("this", this);
    //  currentTarget this 指向一样 事件绑定的对象
    // target 实际触发的对象
    console.log("target", event.target);
    console.log("currentTarget", event.currentTarget);
});
$(input).click(function(event) {
    // keyCOde 获取点击的案件 回车 == 13
    console.log(event.keyCode);
    $("p").text($(this).val); // 获取元素p 内部得文本内容
    if (event.keyCode == 13) {
        // 敲回车 背景颜色变成绿色
        $("p").css("background-color", "green");
    }
});
```

## jq 链式编程

-   链式编程原理 : return this ; 调用 '任何' 一个方法 都是返回了对象本身
-   通常情况下,只有设置操作才能把链式变成延续下去.因为获取操作的时候 会返回获取到的相应的值 无法返回 this

```js
$(obj).click(function() {
    $(this)
        .css("width", "80px")
        .css("font-size", "40px")
        .parent()
        .css("width", "200px")
        .end()
        .css("background-color", "black");
    // 结束当前链最近一次过滤操作, 并且返回匹配元素之前的状态
});
```

## 隐式迭代

-   隐式迭代式: 在方法的内部会为匹配到的所有元素进行循环遍历 执行相应的方法 而不用我们在进行循环,简化我们的操作 方便我们调用
-   如果获取的多元素的值 大部分情况下返回的是第一个元素的值

```js
$(obj).click(function() {
    console.log($(".box").text());
});
```

## each

-   大部分情况下是不需要使用 each 方法的 因为 jq 的隐式迭代特性
-   如果要对每个元素做不用的处理 这时候就要用到 each 方法
-   作用:遍历 jq 对象集合 为每个匹配的元素执行一个函数
-   \$(selector).each(function(index,element){})
-   element 是一个 js 对象 需要转换成 jq 对象

```js
$("li").each(function(index, ele) {
    // ele  当前正在遍历的dom 对象
    // index 当前正在遍历的dom 对象的下标
    console.log('index ==>' , index);
    console.log('ele ==>',ele);
    // 如果下标大于 3 的就绑定点击事件
    if(index > 3){
      ele.onclick = function(){
        console.log('点击事件')
      }
    }
});
```
## 多库共存
+ 此处多库共存指的是：jQuery 占用了$ 和 jQuery 这两个变量。当在同一个页面中引用了 jQuery 这个 js 库，并且引用的其他库（或者其他版本的 jQuery 库）中也用到了$或者 jQuery 这两个变量，那么，要保证每个库都能正常使用，这时候就有了多库共存的问题。
+ $.noConflict();让 jQuery 释放对$的控制权，让其他库能够使用$符号，达到多库共存的目的。此后，只能使用 jQuery 来调用 jQuery 提供的方法