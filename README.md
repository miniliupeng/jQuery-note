# jQuery-note
***一、核心***

jQuery 核心函数  

jQuery([selector,[context]])  这个函数接收一个包含 CSS 选择器的字符串，然后用这个字符串去匹配一组元素  
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
map(callback)                         将一组元素转换成其他数组（不论是否是元素数组）
has(expr|ele)                         保留包含特定后代的元素，去掉那些不含有指定后代的元素。
not(expr|ele|fn)                      从匹配元素的集合中删除与指定表达式匹配的元素
slice(start,[end])                    选取一个匹配的子集

查找
children([expr])                      取得一个包含匹配的元素集合中每一个元素的所有子元素的元素集合。
closest(e|o|e)                        从元素本身开始，逐级向上级元素匹配，并返回最先匹配的元素。
find(e|o|e)                           搜索所有与指定表达式匹配的元素
next([expr])                          取得一个包含匹配的元素集合中每一个元素紧邻的后面同辈元素的元素集合。
nextAll([expr])                       查找当前元素之后所有的同辈元素。
nextUntil([e|e][,f])                  查找当前元素之后所有的同辈元素，直到遇到匹配的那个元素为止。
offsetParent()                        返回第一个匹配元素用于定位的父节点。
parent([expr])                        取得一个包含着所有匹配元素的唯一父元素的元素集合。
parents([expr])                       取得一个包含着所有匹配元素的祖先元素的元素集合
parentsUntil([e|e][,f])               查找当前元素的所有的父辈元素，直到遇到匹配的那个元素为止。
prev([expr])                          取得一个包含匹配的元素集合中每一个元素紧邻的前一个同辈元素的元素集合。
prevAll([expr])                       查找当前元素之前所有的同辈元素
prevUntil([e|e][,f])                  查找当前元素之前所有的同辈元素，直到遇到匹配的那个元素为止。
siblings([expr])                      取得一个包含匹配的元素集合中每一个元素的所有唯一同辈元素的元素集合。

串联
add(e|e|h|o[,c])                      把与表达式匹配的元素添加到jQuery对象中。
andSelf()                             加入先前所选的加入当前元素中
addBack()                             添加堆栈中元素集合到当前集合，一个选择性的过滤选择器。
contents()                            查找匹配元素内部所有的子节点（包括文本节点）。如果元素是一个iframe，则查找文档内容
end()                                 回到最近的一个"破坏性"操作之前。

四、文档处理

内部插入
append(content|fn)                    向每个匹配的元素内部追加内容。
appendTo(content)                     把所有匹配的元素追加到另一个指定的元素元素集合中。
prepend(content|fn)                   向每个匹配的元素内部前置内容。
prependTo(content)                    把所有匹配的元素前置到另一个、指定的元素元素集合中。

外部插入
after(content|fn)                     在每个匹配的元素之后插入内容。
before(content|fn)                    在每个匹配的元素之前插入内容。
insertAfter(content)                  把所有匹配的元素插入到另一个、指定的元素元素集合的后面。
insertBefore(content)                 把所有匹配的元素插入到另一个、指定的元素元素集合的前面。

包裹
wrap(html|ele|fn)                     把所有匹配的元素用其他元素的结构化标记包裹起来。为每一个匹配的元素都包裹一次。
unwrap()                              把所有匹配的元素移出父元素，而且会在DOM结构上替换他们的父元素
wrapAll(html|ele)                     将所有匹配的元素用单个元素包裹起来
wrapInner(html|ele|fn)                将每一个匹配的元素的子内容(包括文本节点)用一个HTML结构包裹起来

替换
replaceWith(content|fn)               将所有匹配的元素替换成指定的HTML或DOM元素。
replaceAll(selector)                  用匹配的元素替换掉所有 selector匹配到的元素。

删除
empty()                               删除匹配的元素集合中所有的子节点。
remove([expr])                        从DOM中删除所有匹配的元素。
detach([expr])                        从DOM中删除所有匹配的元素。

复制
clone([Even[,deepEven]])              克隆匹配的DOM元素并且选中这些克隆的副本。

五、属性

属性
attr(name|pro|key,val|fn)             设置或返回被选元素的属性值。
removeAttr(name)                      从每一个匹配的元素中删除一个属性
prop(n|p|k,v|f)                       获取在匹配的元素集中的第一个元素的属性值。
removeProp(name)                      用来删除由.prop()方法设置的属性集

CSS 类
addClass(class|fn)                    为每个匹配的元素添加指定的类名。
removeClass([class|fn])               从所有匹配的元素中删除全部或者指定的类。
toggleClass(class|fn[,sw])            如果存在（不存在）就删除（添加）一个类。

HTML代码/文本/值
html([val|fn])                        取得第一个匹配元素的html内容。
text([val|fn])                        取得所有匹配元素的内容。
val([val|fn|arr])                     获得匹配元素的当前值。

六、CSS

CSS
css(name|pro|[,val|fn])               访问匹配元素的样式属性。
jQuery.cssHooks                       直接向 jQuery 中添加钩子，用于覆盖设置或获取特定 CSS 属性时的方法，目的是为了标准化 CSS 属性名或创建自定义属性。

位置
offset([coordinates])                 获取匹配元素在当前视口的相对偏移。
position()                            获取匹配元素相对父元素的偏移。
scrollTop([val])                      获取匹配元素相对滚动条顶部的偏移。
scrollLeft([val])                     获取匹配元素相对滚动条左侧的偏移。

尺寸
height([val|fn])                      取得匹配元素当前计算的高度值（px）。
width([val|fn])                       取得第一个匹配元素当前计算的宽度值（px）。
innerHeight()                         获取第一个匹配元素内部区域高度（包括补白、不包括边框）。
innerWidth()                          获取第一个匹配元素内部区域宽度（包括补白、不包括边框）。
outerHeight([options])                获取第一个匹配元素外部高度（默认包括补白和边框）。
outerWidth([options])                 获取第一个匹配元素外部宽度（默认包括补白和边框）。

七、效果

基本
show([s,[e],[fn]])                    显示隐藏的匹配元素。
hide([s,[e],[fn]])                    隐藏显示的元素
toggle([s],[e],[fn])                  用于绑定两个或多个事件处理器函数，以响应被选元素的轮流的 click 事件。

滑动
slideDown([s],[e],[fn])               通过高度变化（向下增大）来动态地显示所有匹配的元素，在显示完成后可选地触发一个回调函数。
slideUp([s,[e],[fn]])                 通过高度变化（向上减小）来动态地隐藏所有匹配的元素，在隐藏完成后可选地触发一个回调函数。
slideToggle([s],[e],[fn])             通过高度变化来切换所有匹配元素的可见性，并在切换完成后可选地触发一个回调函数。

淡入淡出
fadeIn([s],[e],[fn])                  通过不透明度的变化来实现所有匹配元素的淡入效果，并在动画完成后可选地触发一个回调函数。
fadeOut([s],[e],[fn])                 通过不透明度的变化来实现所有匹配元素的淡出效果，并在动画完成后可选地触发一个回调函数。
fadeTo([[s],o,[e],[fn]])              把所有匹配元素的不透明度以渐进方式调整到指定的不透明度，并在动画完成后可选地触发一个回调函数
fadeToggle([s,[e],[fn]])              通过不透明度的变化来开关所有匹配元素的淡入和淡出效果，并在动画完成后可选地触发一个回调函数。

自定义
animate(p,[s],[e],[fn])               用于创建自定义动画的函数。
stop([c],[j])                         停止所有在指定元素上正在运行的动画。
delay(d,[q])                          设置一个延时来推迟执行队列中之后的项目。
finish([queue])                       停止当前正在运行的动画，删除所有排队的动画，并完成匹配元素所有的动画。

设置
jQuery.fx.off                         关闭页面上所有的动画。把这个属性设置为true可以立即关闭所有动画

八、工具

浏览器及特性检测
$.browser.version                     浏览器渲染引擎版本号。

数组和对象操作
$.each(object,[callback])             通用遍历方法，可用于遍历对象和数组。
$.extend([d],tgt,obj1,[objN])         用一个或多个其他对象来扩展一个对象，返回被扩展的对象。
$.grep(array,fn,[invert])             使用过滤函数过滤数组元素。
$.when(deferreds)                     提供一种方法来执行一个或多个对象的回调函数，延迟对象通常表示异步事件。
$.makeArray(obj)                      将类数组对象转换为数组对象。
$.map(arr|obj,callback)               将一个数组中的元素转换到另一个数组中。
$.inArray(val,arr,[from])             确定第一个参数在数组中的位置，从0开始计数(如果没有找到则返回 -1 )。
$.toArray()                           把jQuery集合中所有DOM元素恢复成一个数组。
$.merge(first,second)                 合并两个数组
$.uniqueSort(array)                   $.uniqueSort()函数通过搜索的数组对象，排序数组，并移除任何重复的节点。
$.parseXML(data)                      解析一个字符串到一个XML文件。

函数操作
$.noop                                一个空函数
$.proxy(function,context)             返回一个新函数，并且这个函数始终保持了特定的作用域。

测试操作
$.contains(c,c)                       一个DOM节点是否包含另一个DOM节点。
$.type(obj)                           检测obj的数据类型。
$.isEmptyObject(obj)                  测试对象是否是空对象（不包含任何属性）。
$.isPlainObject(obj)                  测试对象是否是纯粹的对象（通过 "{}" 或者 "new Object" 创建的）。
$.isNumeric(value)                    确定它的参数是否是一个数字。

字符串操作
$.trim(str)                           去掉字符串起始和结尾的空格。
$.param(obj,[traditional])            将表单元素数组或者对象序列化。是.serialize()的核心方法。

插件编写
$.error(message)                      接受一个字符串，并且直接抛出一个包含这个字符串的异常。
$.fn.jquery                           代表 jQuery 版本号的字符串。

九、事件

页面载入
ready(fn)                             当DOM载入就绪可以查询及操纵时绑定一个要执行的函数。

事件处理
on(eve,[sel],[data],fn)               在选择元素上绑定一个或多个事件的事件处理函数。
off(eve,[sel],[fn])                   在选择元素上移除一个或多个事件的事件处理函数。
one(type,[data],fn)                   为每一个匹配元素的特定事件（像click）绑定一个一次性的事件处理函数。
trigger(type,[data])                  在每一个匹配的元素上触发某类事件。
triggerHandler(type, [data])          这个特别的方法将会触发指定的事件类型上所有绑定的处理函数。但不会执行浏览器默认动作，也不会产生事件冒泡。

事件委派

事件切换
hover([over,]out)                     一个模仿悬停事件（鼠标移动到一个对象上面及移出这个对象）的方法。
toggle([spe],[eas],[fn])              用于绑定两个或多个事件处理器函数，以响应被选元素的轮流的 click 事件。

事件
blur([[data],fn])                     当元素失去焦点时触发 blur 事件。
change([[data],fn])                   当元素的值发生改变时，会发生 change 事件。
click([[data],fn])                    触发每一个匹配元素的click事件。
dblclick([[data],fn])                 当双击元素时，会发生 dblclick 事件。
focus([[data],fn])                    当元素获得焦点时，触发 focus 事件。
focusin([data],fn)                    当元素获得焦点时，触发 focusin 事件。
focusout([data],fn)                   当元素失去焦点时触发 focusout 事件
keydown([[data],fn])                  当键盘或按钮被按下时，发生 keydown 事件。
keypress([[data],fn])                 当键盘或按钮被按下时，发生 keypress 事件。
keyup([[data],fn])                    当按钮被松开时，发生 keyup 事件。它发生在当前获得焦点的元素上。
mousedown([[data],fn])                当鼠标指针移动到元素上方，并按下鼠标按键时，会发生 mousedown 事件。
mouseenter([[data],fn])               只有在鼠标指针穿过被选元素时，才会发生 mouseenter 事件。
mouseleave([[data],fn])               只有在鼠标指针离开被选元素时，，发生 mouseleave 事件。
mousemove([[data],fn])                当鼠标指针在指定的元素中移动时，就会发生 mousemove 事件。
mouseout([[data],fn])                 不论鼠标指针离开被选元素还是任何子元素，发生 mouseout 事件。
mouseover([[data],fn])                不论鼠标指针穿过被选元素或其子元素，都会触发 mouseover 事件。
mouseup([[data],fn])                  当在元素上放松鼠标按钮时，会发生 mouseup 事件
resize([[data],fn])                   当调整浏览器窗口的大小时，发生 resize 事件。
scroll([[data],fn])                   当用户滚动指定的元素时，会发生 scroll 事件。
select([[data],fn])                   当 textarea 或文本类型的 input 元素中的文本被选择时，会发生 select 事件
submit([[data],fn])                   当提交表单时，会发生 submit 事件

十、事件对象

eve.currentTarget                     在事件冒泡阶段中的当前DOM元素
eve.data                              当前执行的处理器被绑定的时候，包含可选的数据传递给jQuery.fn.bind。
eve.delegateTarget                    当currently-called的jQuery事件处理程序附加元素。
eve.isDefaultPrevented()              根据事件对象中是否调用过 event.preventDefault() 方法来返回一个布尔值。
event.isImmediatePropagationStopped() 根据事件对象中是否调用过 event.stopImmediatePropagation() 方法来返回一个布尔值。
eve.isPropagationStopped()            根据事件对象中是否调用过 event.stopPropagation() 方法来返回一个布尔值。
eve.namespace                         当事件被触发时此属性包含指定的命名空间。
eve.pageX                             鼠标相对于文档的左边缘的位置。
eve.pageY                             鼠标相对于文档的顶部边缘的位置。
eve.preventDefault()                  阻止默认事件行为的触发。
eve.relatedTarget                     在事件中涉及的其它任何DOM元素。
eve.result                            这个属性包含了当前事件事件最后触发的那个处理函数的返回值，除非值是 undefined 。
event.stopImmediatePropagation()      阻止剩余的事件处理函数执行并且防止事件冒泡到DOM树上。
eve.stopPropagation()                 防止事件冒泡到DOM树上，也就是不触发的任何前辈元素上的事件处理函数。
eve.target                            最初触发事件的DOM元素
eve.timeStamp                         这个属性返回事件触发时距离1970年1月1日的毫秒数。
eve.type                              点击所有锚点后弹出事件类型。
eve.which                             针对键盘和鼠标事件，这个属性能确定你到底按的是哪个键或按钮。

十一、延迟对象

def.done(d,[d])                       当延迟成功时调用一个函数或者数组函数.
def.fail(failCallbacks)               当延迟失败时调用一个函数或者数组函数.。
def.reject(args)                      拒绝延迟对象，并根据给定的参数调用任何失败的回调函数。
def.rejectWith(c,[a])                 拒绝延迟的对象，并根据给定的上下文和参数调用任何失败的回调函数。
def.resolve(args)                     解决递延对象，并根据给定的参数调用任何完成的回调函数。
def.resolveWith(c,[a])                解决递延对象，并根据给定的上下文和参数调用任何完成的回调函数。
def.then(d[,f][,p])                   添加处理程序被调用时，递延对象得到解决或者拒绝。
def.promise([ty],[ta])                返回一个 Promise 对象用来观察当某种类型的所有行动绑定到集合，排队与否还是已经完成。  
def.always(al,[al])                   当递延对象是解决或拒绝时被调用添加处理程序。 
def.notify(args)                      调用一个给定args的递延对象上的进行中的回调 （progressCallbacks） 
def.notifyWith(c,[a])                 去掉字符串起始和结尾的空格。  
def.progress(proCal)                  当Deferred对象时生成进度通知时添加被访问处理程序。
def.state()                           确定一个Deferred对象的当前状态。

十二、回调函数

cal.add(callbacks)                    回调列表中添加一个回调或回调的集合。
cal.disable()                         禁用回调列表中的回调
cal.empty()                           从列表中删除所有的回调.
cal.fire(arguments)                   禁用回调列表中的回调
cal.fired()                           用给定的参数调用所有的回调。
cal.fireWith([c] [,a])                访问给定的上下文和参数列表中的所有回调
cal.has(callback)                     确定是否提供的回调列表
cal.lock()                            锁定在其当前状态的回调列表
cal.locked()                          确定是否已被锁定的回调列表
cal.remove(callbacks)                 删除回调或回调回调列表的集合。
$.callbacks(flags)                    一个多用途的回调列表对象，提供了强大的的方式来管理回调函数列表。

十三、AJAX

ajax 请求
$.ajax(url,[settings])                通过 HTTP 请求加载远程数据。
$.get(url,[data],[fn],[type])         通过远程 HTTP GET 请求载入信息。
$.getJSON(url,[data],[fn])            通过 HTTP GET 请求载入 JSON 数据。
$.getScript(url,[callback])           通过 HTTP GET 请求载入并执行一个 JavaScript 文件。
$.post(url,[data],[fn],[type])        通过远程 HTTP POST 请求载入信息。

ajax 事件
ajaxComplete(callback)                AJAX 请求完成时执行函数。Ajax 事件。
ajaxError(callback)                   AJAX 请求发生错误时执行函数。Ajax 事件。
ajaxSend(callback)                    AJAX 请求发送前执行函数。Ajax 事件。
ajaxStart(callback)                   AJAX 请求开始时执行函数。Ajax 事件。
ajaxStop(callback)                    AJAX 请求结束时执行函数。Ajax 事件。
ajaxSuccess(callback)                 AJAX 请求成功时执行函数。Ajax 事件。

其它
load(url,[data],[callback])           载入远程 HTML 文件代码并插入至 DOM 中。
$.ajaxPrefilter([type],fn)
$.ajaxSetup([options])                设置全局 AJAX 默认选项。
serialize()                           序列表表格内容为字符串。
serializeArray()                      序列化表格元素 (类似 '.serialize()' 方法) 返回 JSON 数据结构数据。
