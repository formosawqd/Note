1. 前端模块化：为了更好的处理得到想要的数据，将数据放在一个js文件里，commonJS是把这个js文件导出，在这个js文件里用module.exports来导出。在想要引用的地方用require来引入，在require的时候还可以结构出来
2. 函数的this指向，指向定义时的执行上下文，或者就是指向外层代码执行上下文
3. 重的set用法： let arr = [1, 2, 3, 4, 6, 3, 6, 7,7, 7, 2, 45, 6];       let newArr = new Set(arr)  得到结果[1, 2,  3, 4, 6, 7, 45]  
4. let o = "formosa";  console.log(Object.prototype.toString.bind(o)());  打印结果：[object String] bind只能改变this,不会执行，如果换成call,apply就可以省略后面的括号
5. 作用域链: 保存一个函数所有可用的作用域对象的链式结构(好友列表)学名就叫作用域链
6. 闭包形成的原因: 外层函数调用后，外层函数的作用域对象被内层函数引用着无法释放，形成了闭包对象
7. 作用域  用途: 一个变量的可用范围       本质: 也是一个专门保存变量的对象
8. 清除浮动最常用的是利用伪元素来清除浮动，谁浮动就给谁的父元素加伪元素，给父元素加伪元素其实就是给父元素加第一个儿子或者最后一个儿子，然后将伪元素设置为块级元素，内容为空，再清除浮动， content: "" ; display: block; clear: both;
9. 因为 js 是单线程运行的，在代码执行的时候，通过将不同函数的执行上下文压入执行栈中来保证代码的有序执行。在执行同步代码的时候，如果遇到了异步事件，js 引擎并不会一直等待其返回结果，而是会将这个事件挂起，继续执行执行栈中的其他任务。当异步事件执行完毕后，再将异步事件对应的回调加入到与当前执行栈中不同的另一个任务队列中等待执行。任务队列可以分为宏任务对列和   微任务对列，当当前执行栈中的事件执行完毕后，js 引擎首先会判断微任务对列中是否有任务可以执行，如果有就将微任务队首的事件压入栈中执行。当微任务对列中的任务都执行完成后再去判断宏任务对列中的任务。 微任务包括了 promise 的回调、node 中的 process.nextTick 、对 Dom 变化监听的 MutationObserver。  宏任务包括了 script 脚本的执行、setTimeout ，setInterval ，setImmediate 一类的定时事件，还有如 I/O 操作、UI 渲染等。
10. Pomise.all的使用：Promise.all可以将多个Promise实例包装成一个新的Promise实例。同时，成功和失败的返回值是不同的，成功的时候返回的是一个结果数组，而失败的时候则返回最先被reject失败状态的值。
11. 什么是闭包：外层函数调用后，外层函数的作用域对象被内层函数引用着无法释放，形成了闭包对象  好处：1 创建私有变量 2使已经结束运行的函数上下文中的变量继续留在内存中， 缺点：多占用内存，使用不当会造成内存泄漏
12. 同源策略：浏览器只允许当前网页中的ajax请求使用自己网站的资源，禁止ajax请求使用其他网站的资源。 浏览器会检查网页请求回来的所有数据。尤其会检查ajax的xhr请求回来的数据。浏览器只允许来源地址和当前网页所在地址属于同一域名下的数据，进入程序中使用。一旦发现，请求回来的数据来源地址，与当前网页所在地址不一致，则浏览器禁止使用该数据
13. Ajax发送异步请求（四步操作）：1 创建异步对象（XMLHttpRequest对象）2 打开与服务器的连接 3 发送请求 4 接收服务器的响应
14. javascript 代码中的 "use strict"; 是什么意思 ? 使用它区别是什么？use strict 指的是严格运行模式，在这种模式对 js 的使用添加了一些限制。比如说禁止 this 指向全局对象，还有禁止使用 with 语句等。设立严格模式的目的，主要是为了消除代码使用中的一些不安全的使用方式，也是为了消除 js 语法本身的一些不合理的地方，以此来减少一些运行时的怪异的行为。同时使用严格运行模式也能够提高编译的效率，从而提高代码的运行速度。我认为严格模式代表了 js 一种更合理、更安全、更严谨的发展方向
15. 什么是vue生命周期？  Vue 实例从创建到销毁的过程，就是生命周期。也就是从开始创建、初始化数据、编译模板、挂载Dom→渲染、更新→渲染、卸载等一系列过程，我们称这是 Vue 的生命周期
16. vue生命周期的作用是什么？ 它的生命周期中有多个事件钩子，让我们在控制整个Vue实例的过程时更容易形成好的逻辑
17. vue生命周期总共有几个阶段？ 它可以总共分为8个阶段：创建前/后, 载入前/后,更新前/后,销毁前/销毁后
18. 第一次页面加载会触发哪几个钩子？第一次页面加载时会触发 beforeCreate, created, beforeMount, mounted 这几个钩子
19. DOM 渲染在 哪个周期中就已经完成？DOM 渲染在 mounted 中就已经完成了。
20. 简单描述每个周期具体适合哪些场景？生命周期钩子的一些使用方法： beforecreate : 可以在这加个loading事件，在加载实例时触发 created : 初始化完成时的事件写在这里，如在这结束loading事件，异步请求也适宜在这里调用 mounted : 挂载元素，获取到DOM节点 updated : 如果对数据统一处理，在这里写上相应函数 beforeDestroy : 可以做一个确认停止事件的确认框 nextTick : 更新数据后立即操作dom
21. Vue生命周期中mounted和created的区别  created:在模板渲染成html前调用，即通常初始化某些属性值，然后再渲染成视图 , mounted:在模板渲染成html后调用，通常是初始化页面完成后，再对html的dom节点进行一些需要的操作。
22. promise.all错误处理： 在promise.all队列中，使用map每一个过滤每一个promise任务，其中任意一个报错后，return一个返回值，确保promise能正常执行走到.then中
23.  slot的应用场景，印象最深的，这两样看的最多的可能就是组件的封装了，运用slot来占位，来自定义自己想要展示的内容，也就是这两天，可能才知道了组件的封装是怎么回事，知道了那些开源的框架组件是怎么封装的，是怎么通过属性来定义我们自己想要的内容的，父组件中的 v-slot:title就等价于#title，还等价于slot='title',给我的感觉是这样，就看自己怎用了，这个是具名插槽，那么在子组件中，就会找到对应的名字，从而把父组件中的自定义的内容放在子组件的对应的位置，还要注意的是，如果用v-slot:title和#title的时候，在外层必须用template来套着，name='title'的话，好像就不需要套template，这是需要注意的地方
24. sourceMap的作用，就是找到源代码和打包之后的代码的映射关系，以至于报错的时候，方便查找自己哪里错了，会显示在源代码，也就是自己写的代码中的错误位置
25. 用了postcss-px-to-viewport之后，内联样式是不生效的，好像暂时只看到了内联的样式是不会生效的，这个插件用于把px转换为视口的宽度值，在我的理解来说，比如给的原型图宽度是30px，然后通过插件转换之后，加入就变成了4vw,然后在我们更改设备的时候，设备变了，宽度也变了，但是4vw还是4vw，这个是不会变的，只是实际所占的宽度改变了，因为现在的设备宽度变了，所4vw就变成了此时设备的4vw,也就跟着转换成了对应的px值，所以才实现了适配，这就是我的理解
26. vue的样式绑定用三元运算符很适合，能够减少大量的重复代码。印象最深刻的是单选框的使用，配合是否选中，决定想要的样式.
27.  很重要很重要很重要，今天学到的一招，以前都没注意过这个问题，就是报错，xxx is not a function 这种问题一般是调用的这个方法的对象出了问题，比如这个方法是给一个数字用的，但是调用的时候没有注意，调方法的这个对象变了，变成了字符串，那么就会报这种错，所以一般在调用方法的时候，一般事先会判断一下对象是否存在或者类型，不然就会报这种错。
28. autoprefixer这个加浏览器前缀的插件，配置好了，npm run build的时候，出现了问题，结果是因为在配置浏览器的那里出了问题，还有就是vue脚手架建项目的时候，就已经安装了autoprefixer这个的，只是没有启用，所以只需要在vue.config.js里面配置一下就行了
29. axios默认的content-type是application/json,network里面是这种形式：{  name:xxx, age:xxx }， 而application/x-www-form-urlencoded这种是formdata这种形式：name:xxx, age:xxx，要看后端需要的是哪种，如果要formdata的形式传参，那就需要QS来系列化，否则就可以不用QS
30. 组件的sync用法，主要是为了使用者方便，比如在父组件中传了个值money到子组件，然后子组件又需要改money的值，我们就在子组件的触发父组件事件那里写成 this.$emit("update:money", xxx);这样就可以修改父组件的money了，不用再写一个父组件的修改事件，触发那里是固定写法，如果要传的值，也是需要修改的值，在父组件中写成:money.sync="money"就可以了
31.  请求数据的处理问题，有时候请求回来的数据直接就可以用了，就不用修改，直接放到自己定义的变量里面就可以了，但是有的时候，返回的数据可能不是我们所需要的格式，所以这个时候就需要在返回的时候，先循环处理一遍返回的数据，先修改一下，以便于使用，还有就是发送请求的时候，如果所发送的数据和我们data里面的数据格式有出入，那么我们不能直接使用data里面的数据，要看情况，有时候需要深拷贝一下，再修改一下格式，然后再发送请求，这样就不会影响到我们data里面的数据，如果直接把data里面的数据修改了，有可能会引起页面渲然出问题，因为改动了data里面的数据，注意
32. 解token值的方法    decodeURIComponent(escape(window.atob('token'.split('.')[1])))
33. 处理发布动态时遇到的图片问题，上传的时候传的是attchId,然后下载下来是乱码，这个时候为了方便一点，直接在请求回来的数据遍历的时候就处理数据，直接在这个时候就把返回来的图片进行处理，改成可以直接放在src里面的格式，这样，不管在哪里用，都不需要再重新处理一次图片，很多数据都是这样，如果在用的时候发现还要进行很多的处理操作，这个时候就可以想想是否合适，是否在获取回来的时候，就怼数据进行处理。在后面引用的时候，就不会那么的麻烦
34. 路由的replace和push的区别就是会不会向 history 栈添加一个新的记录，简单来说就是，如果用的push，返回的时候，会返回到上一页，如果是replace的话，不会返回上一页，而是会回到上一页的上一页，具体情况用的时候就知道了
35. foreach的遍历，是没有返回值的，所以用foreach的时候，都是新建的一个空数组，然后在遍历旧数组的时候，直接把新的值push到新的数组里面去，还要注意的一点就是，如果遍历数据是一个对象，那么在遍历更改的时候就会改变每一项的数据，因为是复杂类型的数据，而如果是简单类型的数据，遍历的时候修改了数据，也不会改变原数组的，注意这一点
36.  foreach遍历是不能用普通的方法来结束循环的，break是不行的，return false也是不行，这个只会终止符合条件的这一次循环，会继续之后的循环，就是说终止了当前的条件执行，并没有终止整个循环的执行，要想终止循环，需要抛出异常的方式来终止执行
37. api封装的时候，尽量还是把参数一起放在api的文件夹里，不要放在组件发请求的地方，因为这个接口可能被不同的组件调用，如果写在组件里面，改的时候，需要改多个组件，如果是放在api里，那么久只需要改api一个地方就可以了。所以尽量写在api文件里，还有就是比如要判断是否登录这种，因为用的地方可能很多，可能不同的场景都需要判断是否登录了，这种也可以统一写一个方法，放utils里面，这样的话，就不需要在要判断状态的组件里都写方法，改起来也比较方便，
38. &&和||的用法，一般经常出现在判断里面，比如if(条件1&&条件2)，如果是&&，如果条件1为真，那么就要看条件2 了，这个时候决定权就在条件2 的手里，所以只要条件1是真，那么就返回条件2 的值，如果是||，只要条件1 为真，就返回条件1的值，因为是或者，有一个为真就是真
