# jQuery-note
jQuery API
一、核心

jQuery 核心函数
jQuery([selector,[context]])          这个函数接收一个包含 CSS 选择器的字符串，然后用这个字符串去匹配一组元素
jQuery(html,[ownerDocument])          根据提供的原始 HTML 标记字符串，动态创建由 jQuery 对象包装的 DOM 元素。同时设置一系列的属性、事件等
jQuery(callback)                      $(document).ready()的简写，当DOM加载完成后要执行的函数
jQuery.readyException( error )        处理包裹在jQuery()中函数同步抛出的错误

jQuery 对象访问
each(callback)                        以每一个匹配的元素作为上下文来执行一个函数
length                                jQuery 对象中元素的个数
selector                              返回传给jQuery()的原始选择器
context                               返回传给jQuery()的原始的DOM节点内容，即jQuery()的第二个参数。如果没有指定，那么context指向当前的文档(document)
get([index])                          取得其中一个匹配的元素。 num表示取得第几个匹配的元素。从0开始，返回的是DOM对象
index([selector|element])             搜索匹配的元素，并返回相应元素的索引值，从0开始计数

数据缓存
data([key],[value])                   在元素上存放或读取数据,返回jQuery对象
removeData([name|list])               在元素上移除存放的数据

队列控制
queue(element,[queueName])            显示或操作在匹配元素上执行的函数队列，queueName默认是 fx
dequeue([queueName])                  从队列最前端移除一个队列函数，并执行他
clearQueue([queueName])               清空对象上尚未执行的所有队列

插件机制
jQuery.fn.extend(object)              扩展 jQuery 元素集来提供新的方法（通常用来制作插件）
jQuery.extend(object)                 扩展jQuery对象本身

多库共存
jQuery.noConflict([extreme])          运行这个函数将变量$的控制权让渡给第一个实现它的那个库

二、选择器

基本
#id                                   根据给定的ID匹配一个元素。
element                               根据给定的元素标签名匹配所有元素。
.class                                根据给定的css类名匹配元素。
*                                     匹配所有元素。
selector1,selector2,selectorN         将每一个选择器匹配到的元素合并后一起返回。

层级
ancestor descendant                   在给定的祖先元素下匹配所有的后代元素。
parent > child                        在给定的父元素下匹配所有的子元素。
prev + next                           匹配所有紧接在 prev 元素后的 next 元素。
prev ~ siblings                       匹配 prev 元素之后的所有 siblings 元素。

基本筛选器
:first                                获取第一个元素。
:not(selector)                        去除所有与给定选择器匹配的元素。
:even                                 匹配所有索引值为偶数的元素，从 0 开始计数。
:odd                                  匹配所有索引值为奇数的元素，从 0 开始计数。
:eq(index)                            匹配一个给定索引值的元素。
:gt(index)                            匹配所有大于给定索引值的元素。
:lang(language)                       选择指定语言的所有元素。
:last                                 获取最后个元素。
:lt(index)                            匹配所有小于给定索引值的元素。
:header                               匹配如 h1, h2, h3之类的标题元素。
:animated                             匹配所有正在执行动画效果的元素。
:focus                                匹配当前获取焦点的元素。
:root                                 选择该文档的根元素。
:target                               选择由文档URI的格式化识别码表示的目标元素。

内容
:contains(text)                       匹配包含给定文本的元素
:empty                                匹配所有不包含子元素或者文本的空元素
:has(selector)                        匹配含有选择器所匹配的元素的元素
:parent                               匹配含有子元素或者文本的元素

可见性
:hidden                               匹配所有不可见元素，或者type为hidden的元素
:visible                              匹配所有的可见元素

属性
[attribute]                           匹配包含给定属性的元素。
[attribute=value]                     匹配给定的属性是某个特定值的元素
[attribute!=value]                    匹配所有不含有指定的属性，或者属性不等于特定值的元素
[attribute^=value]                    匹配给定的属性是以某些值开始的元素
[attribute$=value]                    匹配给定的属性是以某些值结尾的元素
[attribute*=value]                    匹配给定的属性是以包含某些值的元素
[attrSel1][attrSel2][attrSelN]        复合属性选择器，需要同时满足多个条件时使用。

子元素
:first-child                          匹配所给选择器的第一个子元素
:first-of-type                        结构化伪类，匹配E的父元素的第一个E类型的孩子。等价于:nth-of-type(1) 选择器。
:last-child                           匹配最后一个子元素
:last-of-type                         结构化伪类，匹配E的父元素的最后一个E类型的孩子
:nth-child                            匹配其父元素下的第N个子或奇偶元素
:nth-last-child()                     选择所有他们父元素的第n个子元素。计数从最后一个元素开始到第一个。
:nth-last-of-type()                   选择的所有他们的父级元素的第n个子元素，计数从最后一个元素到第一个。
:nth-of-type()                        选择同属于一个父元素之下，并且标签名相同的子元素中的第n个
:only-child                           如果某个元素是父元素中唯一的子元素，那将会被匹配
:only-of-type                         选择所有没有兄弟元素，且具有相同的元素名称的元素。

表单
:input                                匹配所有 input, textarea, select 和 button 元素
:text                                 匹配所有的单行文本框
:password                             匹配所有密码框
:radio                                匹配所有单选按钮
:checkbox                             匹配所有复选框
:submit                               匹配所有提交按钮，不设置type的button也会成为筛选结果
:image                                匹配所有图像域
:reset                                匹配所有重置按钮
:button                               匹配所有按钮
:file                                 匹配所有文件域

表单对象属性
:enabled                              匹配所有可用元素
:disabled                             匹配所有不可用元素
:checked                              匹配所有被选中元素(复选框、单选框等，select中的option)，对于select元素来说，获取选中推荐使用 :selected
:selected                             匹配所有选中的option元素

混淆选择器
$.escapeSelector(selector)            类选择器或者ID选择器中包含一些CSS特殊字符的时候，这个方法基本上与CSS中CSS.escape()方法类似，唯一的区别是jquery中的这个方法支持所有浏览器。

三、筛选

过滤
eq(index|-index)                      获取当前链式操作中第N个jQuery对象，返回jQuery对象，当参数大于等于0时为正向选取，比如0代表第一个，1代表第二个。当参数为负数时为反向选取，比如-1为倒数第一个。
first()                               获取第一个元素
last()                                获取最后个元素
hasClass(class)                       检查当前的元素是否含有某个特定的类，如果有，则返回true。
filter(expr|obj|ele|fn)               筛选出与指定表达式匹配的元素集合。
is(expr|obj|ele|fn)                   根据选择器、DOM元素或 jQuery 对象来检测匹配元素集合，如果其中至少有一个元素符合这个给定的表达式就返回true。
map(callback)
has(expr|ele)
not(expr|ele|fn)
slice(start,[end])

查找
children([expr])
closest(e|o|e)1.7*
find(e|o|e)
next([expr])
nextAll([expr])
nextUntil([e|e][,f])
offsetParent()
parent([expr])
parents([expr])
parentsUntil([e|e][,f])
prev([expr])
prevAll([expr])
prevUntil([e|e][,f])
siblings([expr])

串联
add(e|e|h|o[,c])1.9*
andSelf()1.8-
addBack()1.9+
contents()
end()
