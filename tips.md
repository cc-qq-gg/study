##1.用node打开一个名为node的js文件，结果node无法运行，一直报错，发现文件名不能是node，更改后正常运行。

>2.（string[not array]）.includes('')====>>>>true，
string.indexOf('')====>>>>>>>0，

3.结构赋值重命名，{name:jiji}={name:'coco'}----->jiji==>coco

4.function aa(){console.log(this)}等于（function(){console.log(this)}）

1.（function (window){})(window),window将变量传到匿名函数内部，缩小作用域查找范围，提高查找效率，只找一次就像，声明依赖说明。
2.web服务运行，html，
  1》npm i http-server
   > josn.文件里加“script":{
"start":"http-server -c-l"}
3.npm5前--save才会加入依赖项

4,<template v-if>才有效，v-show不行

5.a.some(i=> i>200)
true,判断是否符合条件，返回布尔值，evrey反之
6.   通过v-model双向绑定复选框状态

7.template 只能使用v-if, not v-show

8.`// 用value方法清空时，实际值被清空，但是v-model是双向绑定，
  // vue是数据驱动，v-model会以后台数据为渲染基础，
 // 只要没有更改数据，就不会影响页面渲染结果
  // console.log(e.target.value)
  // e.target.value=''`

9.     `// 不要在 forEach 遍历中删除数组元素（没法维护索引）
        // this.todos.forEach((item, index) => {
        //   if (item.completed === true) {
        //     this.todos.splice(index, 1)
        //   }
        // })`

10.对于单选框，复选框以及选择框的选项，v-model绑定的值通常是静态字符串，（而复选框也可以是布尔值）

11.可以将值绑定到vue实例的动态属性上，用v-bind实现，该属性的值可以不是字符串，
     <input type="checkbox" v-model="toggle" true-value="yes" false-value="no">
这是value就会分局选中状态确定值。
  单选框：<input type="radio" v-model="pick" v-bind:value="a">   vm.pick=vm.a(选中时》
 选择框：<select v-model="selected>
                <option v-model:value="{numer:123}"> 123</option>
</select>
 选中时vm.selected 是对象



1.cmd set node_dev='development 添加临时系统环境变量，空格会被加入变量值

2.splice 删除：（index，个数）一个参数时，删除并返回从此到最后的项；
   替换：（啊，吧，的），删除完在插入。插入就是将数据放在index，不删除就加入。

3.html页面中引入，使用element组件，使用element 的步骤，vue.js,index.css&&index.js文件，注意index.js必须最后引用。
element组件必须放在vue实例组件内。

4.闭包，
what:是指一个有权访问另一个函数作用域中的变量的函数。
how: 创建方式，就是在一个函数内部创建另一个访问包含函数的变量的函数,它在其他地方调用依然能够访问器包含函数的变量；
why:内部函数的作用域链中包含包含其包含函数的作用域。

5.弹出框一次存在while(true),一直存在翻译过来就是无限循环

6.vue中计算属性默认只有getter函数，setter按需使用

7.组件的name值，作用：1》递归组件时循环引用2》取消某个页面的缓存是也会用到，keep-alive标签里的exclude=“单页组件命"3》vue开发工具可以看到组件名

8.localStorage的数据空咦长期保存其键值以字符串形式储存，sessionStorage的数据会在页面借宿是被清除。两者都特定于页面的协议。

9.watch：监听器是监听一个属性的变化，触发函数。computed：计算属性，监听一个属性的依赖，一旦依赖改变，则重新计算。大多数情况下，计算属性更合适。而需要在数据变化是执行医嘱或开销较大的操作时，watch更有用。

10.class属性用数组绑定中使用对象，

11.vue组件上添加的class属性会添加到根元素上且不会覆盖根元素上的值。

12，绑定内联样式v-bind:style="{color:color,fontSize:fontSize}"，实则为一个JavaScript对象，css属性名可用驼峰或者短横线分割。推荐直接绑定一个对象，一线的更清晰。v-bind:style="[baseStyle,overf]",数组语法将多个数组语法绑定到一个元素上。

13.template当做不可见的包裹元素，最终不会渲染到页面上。

14.vue会尽可能的高效渲染页面，尽可能的复用之前的元素。但是有的场景下这个特性并不符合实际要求，解决方案就是为其加上唯一的key值，告诉它“不要复用它们”

15，v-if是真正的条件渲染，在切换过程中销毁和重建相应的监听器和子组件。2>惰性，true渲染，when false do nothing2》也v-show的区别是：后者无论真假都会渲染，并指示简单的进行css的display切换。

16.v-if和v-for一起使用时，后者具有更高的优先级。

17of代替in，做分隔符是因为前者最接近JavaScript迭代器的语法。

18.v-for对象时，按Object.keys()的结果遍历，不同JavaScript引擎下的结果可能不一致（item,key,index)参数分别是值，健名，索引值。

19.建议尽量v-for是提供key，除非内容非常简单或可以依赖默认行为提高性能。

20，不要使用对象或数组之类的分为原始类型值作为v-for的key。用字符串或书类型的值取而代之。

21.数组更新vue，七个数组方法（splice,push,shift,unshift,pop,reverse,sort）;2>>或者替换数组（filter（），concat（），slice（）），数组变化并不会导致重新渲染整个列表，vue为使dom元素最大范围重用二实现了一些智能启发式方法，因此一些含相同元素的数组替换原来数组非常高效。

22，有用JavaScript的限制，vue不能自动检测以下的数组变动无法动态更新：1>用索引直接设置元素，2》修改数组的长度。
解决方案：1>Vue.set(vm.items,indexOfItme,newValue);2>Vue.items.splice(indexOfItem,1,newValue)3>vm.#set(vm.items,indexOfItem,newValue)
对象也有类似的JavaScript的限制，Vue不能检测到对象属性的IM家或删除；解决方法1》Vue.set(vm.object,key,value)添加相应属性2》vm.$set(vm.object,key,value)3》添加多个新属性，用两个对象的属性创建一个行的对象，vm.userProfile = Object.assign({}, vm.userProfile, {
  age: 27,
  favoriteColor: 'Vue Green'
})

23.delete object.key删除对象属性

24.显示过滤/排序结果（显示一个数组的过滤哦排序副本）：方法：创建一个返回过滤或排序数组的计算属性2》计算属性不适用的情况下（比如v-for）可以使用methods;主要思想不变。v-for可取整。

25，v-for和v-if1》筛选一定条件的todos<li v-for="todo in todos" v-if="!todo.isComplete">
  {{ todo }}
</li>2》有条件的跳过循环<ul v-if="todos.length">
  <li v-for="todo in todos">
    {{ todo }}
  </li>
</ul>
<p v-else>No todos left!</p>

26.webpack-web-server默认不支持ip访问页面，修改配置项，在pacageke.json中scripts：dev项下webpack-dev-server  加上--host 0.0.0

27.去哪vue手机测试字母拖动页面跟着拖动，解决touchstart.prevent，加上修饰符就完事
28.真机测试可能出现白屏，原因可能是手机浏览器不支持promise，解决方法  npm install bable-polyfill,判断如果浏览器没有promise会自动添加这些
新特性，然后main.js引入babel-polyfill,最后所有浏览器都支持promise

3,将页面文件放在WWWw文件夹下，启动phpstudy后打开apache和mysql，访问127.0.0.1加上路径就开启了本地服务

4.：click.stop='dothis'>>组织单机事件继续传播
：submit:prevent='onSubmit'>>>提交事件不在重载页面
:submit.prevent>>>>只有修饰符
:click.capture='tosothis'>>>监听事件使用补货模式，即元素自身出发的事件现在次处理，然后才有黁在内部元素处理
:click.self='dothis'>>>>元素时自身是触发，不是从内部触发。
修饰符可以串联！！！
!!!!!!!
：click.prevent.self>>>>组织说有的点击
：click.self.prevent>>>>组织对元素自身的点击
:click.once='click'>>>点击事件触发一次，且可以用在组件事件上，

5.：scroll.passive='onscroll'>>>屯东事件的默认行为（滚动）将会立即触发而不会等待onScroll完成，.passive修饰符友情提升移动端的性能。

6.！！！！.passive和.perevent不要一起使用，.prevent会被忽略，.passive告诉浏览器不想组织事件的默认行为。

7.vue通过全局内置自定义按键修饰符别名：Vue.config.keyCodes.f1 = 12；系统修饰符：<Alt + C>-->><input @keyup.alt.67='clear'>;<!--Ctrl + Click-->------>@click.ctrl='doSomething';单独使用ctrl键keyup.17

8..exact修饰符，精确控制系统修饰符组合触发的事件，@click.ctrl="onClick"----->Alt或Shift被一同按下也会触发；@click.ctrl.exact='onCtrlClick'----->有且只有Ctrl被按下时才触发


1.（function (window){})(window),window将变量传到匿名函数内部，缩小作用域查找范围，提高查找效率，只找一次就像，声明依赖说明。
2.web服务运行，html，
  1》npm i http-server
   > josn.文件里加“script":{
"start":"http-server -c-l"}
3.npm5前--save才会加入依赖项

4,<template v-if>才有效，v-show不行

5.a.some(i=> i>200)
true,判断是否符合条件，返回布尔值，evrey反之
6.   通过v-model双向绑定复选框状态

7.template 只能使用v-if, not v-show

8.// 用value方法清空时，实际值被清空，但是v-model是双向绑定，
                // vue是数据驱动，v-model会以后台数据为渲染基础，
                // 只要没有更改数据，就不会影响页面渲染结果
                // console.log(e.target.value)
                // e.target.value=''

9.     // 不要在 forEach 遍历中删除数组元素（没法维护索引）
        // this.todos.forEach((item, index) => {
        //   if (item.completed === true) {
        //     this.todos.splice(index, 1)
        //   }
        // })

10.对于单选框，复选框以及选择框的选项，v-model绑定的值通常是静态字符串，（而复选框也可以是布尔值）

11.可以将值绑定到vue实例的动态属性上，用v-bind实现，该属性的值可以不是字符串，
     <input type="checkbox" v-model="toggle" true-value="yes" false-value="no">
这是value就会分局选中状态确定值。
  单选框：<input type="radio" v-model="pick" v-bind:value="a">   vm.pick=vm.a(选中时》
 选择框：<select v-model="selected>
                <option v-model:value="{numer:123}"> 123</option>
</select>
 选中时vm.selected 是对象



1.cmd set node_dev='development 添加临时系统环境变量，空格会被加入变量值

2.splice 删除：（index，个数）一个参数时，删除并返回从此到最后的项；
   替换：（啊，吧，的），删除完在插入。插入就是将数据放在index，不删除就加入。

3.html页面中引入，使用element组件，使用element 的步骤，vue.js,index.css&&index.js文件，注意index.js必须最后引用。
element组件必须放在vue实例组件内。

4.闭包，
what:是指一个有权访问另一个函数作用域中的变量的函数。
how: 创建方式，就是在一个函数内部创建另一个访问包含函数的变量的函数,它在其他地方调用依然能够访问器包含函数的变量；
why:内部函数的作用域链中包含包含其包含函数的作用域。

5.弹出框一次存在while(true),一直存在翻译过来就是无限循环

6.vue中计算属性默认只有getter函数，setter按需使用

7.组件的name值，作用：1》递归组件时循环引用2》取消某个页面的缓存是也会用到，keep-alive标签里的exclude=“单页组件命"3》vue开发工具可以看到组件名

8.localStorage的数据空咦长期保存其键值以字符串形式储存，sessionStorage的数据会在页面借宿是被清除。两者都特定于页面的协议。

9.watch：监听器是监听一个属性的变化，触发函数。computed：计算属性，监听一个属性的依赖，一旦依赖改变，则重新计算。大多数情况下，计算属性更合适。而需要在数据变化是执行医嘱或开销较大的操作时，watch更有用。

10.class属性用数组绑定中使用对象，

11.vue组件上添加的class属性会添加到根元素上且不会覆盖根元素上的值。

12，绑定内联样式v-bind:style="{color:color,fontSize:fontSize}"，实则为一个JavaScript对象，css属性名可用驼峰或者短横线分割。推荐直接绑定一个对象，一线的更清晰。v-bind:style="[baseStyle,overf]",数组语法将多个数组语法绑定到一个元素上。

13.template当做不可见的包裹元素，最终不会渲染到页面上。

14.vue会尽可能的高效渲染页面，尽可能的复用之前的元素。但是有的场景下这个特性并不符合实际要求，解决方案就是为其加上唯一的key值，告诉它“不要复用它们”

15，v-if是真正的条件渲染，在切换过程中销毁和重建相应的监听器和子组件。2>惰性，true渲染，when false do nothing2》也v-show的区别是：后者无论真假都会渲染，并指示简单的进行css的display切换。

16.v-if和v-for一起使用时，后者具有更高的优先级。

17of代替in，做分隔符是因为前者最接近JavaScript迭代器的语法。

18.v-for对象时，按Object.keys()的结果遍历，不同JavaScript引擎下的结果可能不一致（item,key,index)参数分别是值，健名，索引值。

19.建议尽量v-for是提供key，除非内容非常简单或可以依赖默认行为提高性能。

20，不要使用对象或数组之类的分为原始类型值作为v-for的key。用字符串或书类型的值取而代之。

21.数组更新vue，七个数组方法（splice,push,shift,unshift,pop,reverse,sort）;2>>或者替换数组（filter（），concat（），slice（）），数组变化并不会导致重新渲染整个列表，vue为使dom元素最大范围重用二实现了一些智能启发式方法，因此一些含相同元素的数组替换原来数组非常高效。

22，有用JavaScript的限制，vue不能自动检测一下数组的变动无法动态更新：1>用索引直接设置元素，2》修改数组的长度。
解决方案：1>Vue.set(vm.items,indexOfItme,newValue);2>Vue.items.splice(indexOfItem,1,newValue)3>vm.#set(vm.items,indexOfItem,newValue)
对象也有类似的JavaScript的限制，Vue不能检测到对象属性的IM家或删除；解决方法1》Vue.set(vm.object,key,value)添加相应属性2》vm.$set(vm.object,key,value)3》添加多个新属性，用两个对象的属性创建一个行的对象，vm.userProfile = Object.assign({}, vm.userProfile, {
  age: 27,
  favoriteColor: 'Vue Green'
})

23.delete object.key删除对象属性

24.显示过滤/排序结果（显示一个数组的过滤哦排序副本）：方法：创建一个返回过滤或排序数组的计算属性2》计算属性不适用的情况下（比如v-for）可以使用methods;主要思想不变。v-for可取整。

25，v-for和v-if1》筛选一定条件的todos<li v-for="todo in todos" v-if="!todo.isComplete">
  {{ todo }}
</li>2》有条件的跳过循环<ul v-if="todos.length">
  <li v-for="todo in todos">
    {{ todo }}
  </li>
</ul>
<p v-else>No todos left!</p>

26.webpack-web-server默认不支持ip访问页面，修改配置项，在pacageke.json中scripts：dev项下webpack-dev-server  加上--host 0.0.0

27.去哪vue手机测试字母拖动页面跟着拖动，解决touchstart.prevent，加上修饰符就完事
28.真机测试可能出现白屏，原因可能是手机浏览器不支持promise，解决方法  npm install bable-polyfill,判断如果浏览器没有promise会自动添加这些
新特性，然后main.js引入babel-polyfill,最后所有浏览器都支持promise

3,将页面文件放在WWWw文件夹下，启动phpstudy后打开apache和mysql，访问127.0.0.1加上路径就开启了本地服务

4.：click.stop='dothis'>>组织单机事件继续传播
：submit:prevent='onSubmit'>>>提交事件不在重载页面
:submit.prevent>>>>只有修饰符
:click.capture='tosothis'>>>监听事件使用补货模式，即元素自身出发的事件现在次处理，然后才有黁在内部元素处理
:click.self='dothis'>>>>元素时自身是触发，不是从内部触发。
修饰符可以串联！！！
!!!!!!!
：click.prevent.self>>>>组织说有的点击
：click.self.prevent>>>>组织对元素自身的点击
:click.once='click'>>>点击事件触发一次，且可以用在组件事件上，

5.：scroll.passive='onscroll'>>>屯东事件的默认行为（滚动）将会立即触发而不会等待onScroll完成，.passive修饰符友情提升移动端的性能。

6.！！！！.passive和.perevent不要一起使用，.prevent会被忽略，.passive告诉浏览器不想组织事件的默认行为。

7.vue通过全局内置自定义按键修饰符别名：Vue.config.keyCodes.f1 = 12；系统修饰符：<Alt + C>-->><input @keyup.alt.67='clear'>;<!--Ctrl + Click-->------>@click.ctrl='doSomething';单独使用ctrl键keyup.17

8..exact修饰符，精确控制系统修饰符组合触发的事件，@click.ctrl="onClick"----->Alt或Shift被一同按下也会触发；@click.ctrl.exact='onCtrlClick'----->有且只有Ctrl被按下时才触发

1.删除数组的某项就要找到其索引，findIndex()

2.过滤器vue，本质是函数，常用途是格式化数据，因此必须函数必须return，how：在JavaScript表达式尾部添加“| 过滤器”， <span>{{ dt | 过滤器的名称 }}</span><span :title="dt | 过滤器的名称"></span>1》全局过滤器：Vue.filter('filter',function(origin){...return}2》私有过滤器：vue实例中，一级位置声明filters成员3》参数：过滤器的第一个参数默认为表达式的值，不用传；过滤器的接收的第一实参是函数内部的第二形参；

3.`Vue.$mount();render(create){
return create(标签，标签内部包含的信息)     //创建一个标签
}`
4.async和await结合起来，可以使得异步调用不返回Promise，直接返回then参数方法的参数，代码简洁，异步调用顺序执行。
5.插值表达式只能用在元素的内容区域；不能用在元素的属性节点中
6.鼠标按钮修饰符，限制处处函数响应特定鼠标按钮触发。.left,.right,.middle
6.为什么在HTML中监听事件？
1》看一眼模板就可以轻松定位JavaScript代码里对应的方法2》无需在JavaScript中手动绑定事件，ViewModel代码可以是非常纯粹的逻辑，和dom完全解耦，更易于测试。3》当一个ViewModel被销毁时，说有事件处理器自动删除。
7.npm包全局安装目录路径问题，关键在于修改安装程序默认路径

8.继承铺垫：许多OO语言支持：1》接口继承，只是继承方法；实现继承，继承实际方法。函数没有签名，ECMAScritpt无法实现接口继承，支持实现继承，主要依靠原型链作为实现继承的主要方法，基本思想：利用原型让一个引用类型继承另一个引用类型的属性和方法。2》原型，构造函数，实例的关系：每个构造函数都有一个原型对象，每个原型对象都有一个指向构造函数的指针，实例包含一个指向原型对象的内部指针，加入让原型对象指向另一个类型的实例，西施原型对象将包含另一个原型的指针，相应的另一个原型也包含着一个指向另一个构造函数的指针，如此层层递进，就构成了实例也原型的链条。

9.路由就是根据网址不同返回同页面。 router-view显示的是各个路径所对应路由地址的内容

10.node无法下载或者下载很慢，但之前可以正常下载，how：1》修改镜像2》修改镜像

11.vue表单v-model会忽略表参元素的value,checked,selected初始值，以vue实例数据为准。1》text.textarea,vaule属性和input事件。2》checkbox和radio，checked属性卡和change事件。3》select字段将value作为prop，change作为事件。

12.vue表单v-mode，多个复选框，绑定到同一个数组，点击会获取其中的value值。1》单选按钮，可以绑定到同一数组或字符串。2》选择框， <select v-model="selected">
    <option disabled value="">请选择</option>，绑定到字符串，如果v-model表达式初始值没有匹配到热河项，<select>会被渲染为“未选中状态”，ios不会触发change事件，推荐提供一个空值作为禁选项。2>>>多选是绑定到同一个数组。3》用v-for渲染动态选项：`《select v-model='selected'><option v-for='option in options" v-bind:value='option.value'`.4》单选框，复选框，选择框绑定的值通常是字符串，复选框也可以布尔值。



13.把值绑定到Vue实例的一个动态属性上，该值可以补充字符串<input
  `type="checkbox"
  v-model="toggle"
  true-value="yes"
  false-value="no"`
>。1》表单输入绑定修饰符，.lazy将input转为与change事件同步。.number自动将用户输入值转为数字类型，v-model.number='age',.v-model.trim='msg',自动过滤首尾空白字符

14.一个组件的data选项必须是个函数，因此每个实例可以维护一份呗返回对象的独立的拷贝。

15.组件命名，当使用首字母大写命名组件，也可以用短横线分割的方式使用组件名。注意尽管如此， 直接在DOM（即非字符串的魔板）中只有短横线分割才有效。

16.局部注册的组件总的其子组件中不可用！！！如果希望componentB中使用componentA>>>>>>var ComponentA = { /* ... */ }
17.HTML中特性名大小写不敏感，会吧大写转为小写，因此驼峰命名的属性要用等价的短横线分割命名。
18.prop传一个布尔值，<!-- 包含该 prop 没有值的情况在内，都意味着 `true`。-->
<blog-post is-published></blog-post>1》传一个数组，<!-- 即便数组是静态的，我们仍然需要 `v-bind` 来告诉 Vue -->
<!-- 这是一个 JavaScript 表达式而不是一个字符串。-->
<blog-post v-bind:comment-ids="[234, 266, 273]"></blog-post>2》对象亦如此！！3》一个对象的所有属性作为prop，obj:{},v-bind:'obj'4》子组件中使用其他子组件：
`var ComponentB = {
  components: {
    'component-a': ComponentA
  },
  // ...
}或者，import ComponentA from './ComponentA.vue'
export default {
  components: {
    ComponentA
  },
  // ...`
}》》》》》全局导入基础组件，require.context,全局注册的行为必须在根Vue实例创建之前发生。
19.两种常见的试图改变一个prop的情形1》这个prop用来传递一个初始值，然后子组件希望将其作为一个本利prop数据来使用。props: `['initialCounter'],
data: function () {
  return {
    counter: this.initialCounter
  }
}2》这个prop以一种原始的值传入且需要转换。这种情况下最好用这个prop的值来定义一个计算属性：props: ['size'],
computed: {
  normalizedSize: function () {
    return this.size.trim().toLowerCase()
  }
}`
1.`axios.defaults.baseURL='http://127.0.0.1:3006/;Vue.prototype.$http=axios》》》》至此每个Vue实例都有设置了默认baseURL的axios》》this.$http.get()`
2.node --experimental-modules main.mjs>>>>>>node中使用es模块，仅限测试阶段

3.`export必须输出对外的接口，1》export const a=1；2》const a=1;export {a};3》const a=1; export {a as b}!!!export `语句输出的接口语气对应的值是动态绑定关系。不能再函数内部使用，因为这样无法做静态优化，违背了模块的设计初衷。

4.import命令：import {} from 必须与引入文件的对外接口名称相同。import命令输入的变量都是只读的，因为他的本质是输入接口，不能改写接口，如果a是一个对象改写a的属性是允许的，并且其他模块能够读取改写后的值。

5.import 后面的from指定文件位置，可相对可绝对路径，.js文件可省略，如果只有模块名，没有路径必须有配置文件。2》import命令具有提升效果，提升到整个模块头部，首先执行，有点像es5里的与解析，本质原因是import是变异阶段执行的，在代码执行之前。3》import静态执行，所以不能使用表达式和变量，这些只有在运行时才能得到结果的语法。4》import执行加载的模块，import"loasah",5》模块的整体加载：* 制定一个对象，所有输出值都加载在这个对象上面，import * as circle from '/filepath/filename'!!!!!!注意，模块整体加载所在的那个对象应该是可以静态分析的，所以不允许运行时改变。

6.单页应用：1》优点：良好的交互体验，避免了不必要的跳转和重复渲染，前后端分离，结构清晰，前端负责逻辑，后端负责数据；减轻服务器压力，只管数据，不管逻辑和页面合成。
缺点：初次加载韩式较多（解决方案：模块化管理），不利于搜索引擎优化，前进后退路由管理（解决方案：原生H5HistoryAPI，）

7，export default 指定模块默认输出，接收时可自定义变量名，且不用写大括号。本质上，exportdefault就是输出一个叫做default的变量或方法，然后系统允许你为他去任意名字。因此，export {add as default}>>>>>import {default as foo}是可以的，正是因为，export default的含义是将值赋值个变量default，所以其后面不能跟变量声明语句。至此，export 和export default的区别就是，前者需要手动指定接口，后者指定了默认的接口default

8.export与import的复合写法：`export{foo,bar} from 'my_module";======>>>import {foo,bar} from 'modules';export {foo.bar},实际上foo和bar没有被导入当前模块，只是转接了接口;2》具名接口墨粉接口写法如下：export { es6 as default } from './someModule'========'import { es6 } from './someModule':export default es6;`

9.跨模块常量，因为const命令声明的常量只在当前代码块有效，多个模块引用同一个模块。2》如果常量非常多，可以将这些文件合并在一个indexjs下

10.获取url查询字符串为对象，`var str=window.location.search;
function toObj(str){
var obj={}
  str.split('&').forEach(item =>{
obj[item.split('=')[0]]=item.split('=')[1]}
}`

10.父组件向子组件传入的class和style不会覆盖子组件模板上的class和style，而是合并。


1.确定原型和实例的关系：1》instanceof；2》

2，数组去重，obj=[...new Set(arr)],展开运算符，数组最大值，Math.max(...arr),数组求和：arr.reduce((and ,item,index,arr)and+item),0)

3.基本类型和引用类型的区别：1》基本类型：其值不可变，比如修改字符串后返回的是它的一个副本，原字符串并没有变；比较的是他们的值，比较值会进行隐式转换。2》==进行值的比较，===进行值和数据类型的比较。3》基本类型的变量存放在栈内存中，包含其标识符和其值。4》引用类型，统称为Object类型，细分有：Object,Array,Date,RegExp,Function。引用类型的值是可变的，对其的操作会改变值本身。引用类型的比较是引用的比较，一个空对象不等于另一个空对象，因为两者的值不一样，引用地址不一样。5》引用类型的值保存在堆内存中，js不能直接操对象的内存空间。

4.拷贝继承中，forin循环可以循环构造函数prototype内的属性和方法，





