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
23. slot的应用场景，印象最深的，这两样看的最多的可能就是组件的封装了，运用slot来占位，来自定义自己想要展示的内容，也就是这两天，可能才知道了组件的封装是怎么回事，知道了那些开源的框架组件是怎么封装的，是怎么通过属性来定义我们自己想要的内容的，父组件中的 v-slot:title就等价于#title，还等价于slot='title',给我的感觉是这样，就看自己怎用了，这个是具名插槽，那么在子组件中，就会找到对应的名字，从而把父组件中的自定义的内容放在子组件的对应的位置，还要注意的是，如果用v-slot:title和#title的时候，在外层必须用template来套着，name='title'的话，好像就不需要套template，这是需要注意的地方
24. sourceMap的作用，就是找到源代码和打包之后的代码的映射关系，以至于报错的时候，方便查找自己哪里错了，会显示在源代码，也就是自己写的代码中的错误位置
25. 用了postcss-px-to-viewport之后，内联样式是不生效的，好像暂时只看到了内联的样式是不会生效的，这个插件用于把px转换为视口的宽度值，在我的理解来说，比如给的原型图宽度是30px，然后通过插件转换之后，加入就变成了4vw,然后在我们更改设备的时候，设备变了，宽度也变了，但是4vw还是4vw，这个是不会变的，只是实际所占的宽度改变了，因为现在的设备宽度变了，所4vw就变成了此时设备的4vw,也就跟着转换成了对应的px值，所以才实现了适配，这就是我的理解
26. vue的样式绑定用三元运算符很适合，能够减少大量的重复代码。印象最深刻的是单选框的使用，配合是否选中，决定想要的样式.
27. 很重要很重要很重要，今天学到的一招，以前都没注意过这个问题，就是报错，xxx is not a function 这种问题一般是调用的这个方法的对象出了问题，比如这个方法是给一个数字用的，但是调用的时候没有注意，调方法的这个对象变了，变成了字符串，那么就会报这种错，所以一般在调用方法的时候，一般事先会判断一下对象是否存在或者类型，不然就会报这种错。
28. autoprefixer这个加浏览器前缀的插件，配置好了，npm run build的时候，出现了问题，结果是因为在配置浏览器的那里出了问题，还有就是vue脚手架建项目的时候，就已经安装了autoprefixer这个的，只是没有启用，所以只需要在vue.config.js里面配置一下就行了
29. axios默认的content-type是application/json,network里面是这种形式：{  name:xxx, age:xxx }， 而application/x-www-form-urlencoded这种是formdata这种形式：name:xxx, age:xxx，要看后端需要的是哪种，如果要formdata的形式传参，那就需要QS来系列化，否则就可以不用QS
30. 组件的sync用法，主要是为了使用者方便，比如在父组件中传了个值money到子组件，然后子组件又需要改money的值，我们就在子组件的触发父组件事件那里写成 this.$emit("update:money", xxx);这样就可以修改父组件的money了，不用再写一个父组件的修改事件，触发那里是固定写法，如果要传的值，也是需要修改的值，在父组件中写成:money.sync="money"就可以了
31. 请求数据的处理问题，有时候请求回来的数据直接就可以用了，就不用修改，直接放到自己定义的变量里面就可以了，但是有的时候，返回的数据可能不是我们所需要的格式，所以这个时候就需要在返回的时候，先循环处理一遍返回的数据，先修改一下，以便于使用，还有就是发送请求的时候，如果所发送的数据和我们data里面的数据格式有出入，那么我们不能直接使用data里面的数据，要看情况，有时候需要深拷贝一下，再修改一下格式，然后再发送请求，这样就不会影响到我们data里面的数据，如果直接把data里面的数据修改了，有可能会引起页面渲然出问题，因为改动了data里面的数据，注意
32. 解token值的方法    decodeURIComponent(escape(window.atob('token'.split('.')[1])))
33. 处理发布动态时遇到的图片问题，上传的时候传的是attchId,然后下载下来是乱码，这个时候为了方便一点，直接在请求回来的数据遍历的时候就处理数据，直接在这个时候就把返回来的图片进行处理，改成可以直接放在src里面的格式，这样，不管在哪里用，都不需要再重新处理一次图片，很多数据都是这样，如果在用的时候发现还要进行很多的处理操作，这个时候就可以想想是否合适，是否在获取回来的时候，就怼数据进行处理。在后面引用的时候，就不会那么的麻烦
34. 路由的replace和push的区别就是会不会向 history 栈添加一个新的记录，简单来说就是，如果用的push，返回的时候，会返回到上一页，如果是replace的话，不会返回上一页，而是会回到上一页的上一页，具体情况用的时候就知道了
35. foreach的遍历，是没有返回值的，所以用foreach的时候，都是新建的一个空数组，然后在遍历旧数组的时候，直接把新的值push到新的数组里面去，还要注意的一点就是，如果遍历数据是一个对象，那么在遍历更改的时候就会改变每一项的数据，因为是复杂类型的数据，而如果是简单类型的数据，遍历的时候修改了数据，也不会改变原数组的，注意这一点
36. foreach遍历是不能用普通的方法来结束循环的，break是不行的，return false也是不行，这个只会终止符合条件的这一次循环，会继续之后的循环，就是说终止了当前的条件执行，并没有终止整个循环的执行，要想终止循环，需要抛出异常的方式来终止执行
37. api封装的时候，尽量还是把参数一起放在api的文件夹里，不要放在组件发请求的地方，因为这个接口可能被不同的组件调用，如果写在组件里面，改的时候，需要改多个组件，如果是放在api里，那么久只需要改api一个地方就可以了。所以尽量写在api文件里，还有就是比如要判断是否登录这种，因为用的地方可能很多，可能不同的场景都需要判断是否登录了，这种也可以统一写一个方法，放utils里面，这样的话，就不需要在要判断状态的组件里都写方法，改起来也比较方便，
38. &&和||的用法，一般经常出现在判断里面，比如if(条件1&&条件2)，如果是&&，如果条件1为真，那么就要看条件2 了，这个时候决定权就在条件2 的手里，所以只要条件1是真，那么就返回条件2 的值，如果是||，只要条件1 为真，就返回条件1的值，因为是或者，有一个为真就是真
39. Object.assign(target,source)只会把source可枚举的属性给target
40. Cannot assign to read only property xxxx   不能给一个只读属性赋值
41. Dotenv 是一个零依赖的模块，它能将环境变量中的变量从 .env 文件加载到 process.env 中  https://juejin.cn/post/6844904198929121288
42. HMR:热模块替换，一个模块发生变化，只会重新打包这一个模块，而不是打包所有模块，提升构建速度，样式文件是可以使用HMR功能的，因为内部的style-loader实现了，但是HTML本身就是一个文件，一个模块，所以对html文件是不生效的，js文件默认是不能使用的，但是修改之后是可以使用HMR功能的，HMR功能只对入口之外的其他文件生效
43. eslint-loader和babel-loader是有先后的顺序的，只能eslint先执行，所以要在eslint那里设置enforece:pre，这句话就是强制优先执行
44. oneOf只能匹配一个，也就是说同一个类型的文件被两个loader打包，两个loader是被包裹在oneOf里面的，那么只会执行其中的一个loader，所以为了避免这种情况，需要把另一个Loader放在oneOf的外面，oneOf的作用是为了一个文件不会被多次的打包-------感觉有点不对呀
45. 缓存问题：babel缓存，只需要在babel-loader处加上cacheDirectory:true就可以了，文件的缓存需要用hash值来解决，就是直接在输出文件的输出名字那里加上hash值，hash是webapck打包构建时会生成的唯一的hash值，如果用hash，还是解决不了css和js的缓存问题，修改其中一个文件，两个文件的hash值都是一样的，缓存也会失效，如果是用chunkhash，chunkhash是根据chunk生成的hash值，如果打包来源于同一个chunk，那么hash值就是一样的，由于css实在js中被引入的，所以还是属于同一个chunk，生成的hash值还是一样的，也解决不了缓存的问题，最后一种就是contenthash，这个值是根据文件的内容生成的，不同的文件，contenthash值肯定不一样，如果修改了css文件，js是肯定不会被影响到的，js还是会用缓存，但是css就是修改后的css，这样就解决了缓存的问题
46. ajax失败的回调是请求接口出问题时的回调，是还没有请求到数据，与接口无关
47. 使用express写的接口，是要拼接的，一般的具体的接口文件不用写路径，在express.js文件里统一写路径就行了，如果在具体的接口文件那里也写了路径的话，那么就需要拼接，不然前端发请求的时候，是请求不到想要的数据的，因为请求的接口都不对
48. css-loader是将css文件变成commonjs模块加载到js文件中，style-loader的作用是在head中创建style标签，并且将打包好的js中的阴阳师资源添加到head里面
49. 如果要把css文件分离，就需要一个分离css的插件，minicssextractplugin，如果要分离的话，那么style-loader那里就需要改一下，不需要在head那里创建style标签，改成minicssextractplugin.loader就可以了，这样css就分离出来了，注意插件都需要在plugin那里new 一下，还可以更改一下分离出来的css名字，并且单独放在一个css文件夹里面
50. 设置node的环境变量要使用 process.env.NODE_ENV='development'或者‘production’
51. eslint设置下一行不生效    eslint-disable-next-line
52. 打包的入口可以有3种形式，最常见的就是string形式，单入口打包
53. new的本质，第5点就是为什么要判断返回值类型的原因了，如果函数有返回值，那么就要返回构造函数的返回值，如果构造函数没有返回值，那么就返回新创建的这个对象

    1. 创建一个对象
    2. 将对象的[[prototype]]赋值为构造函数的prototype属性
    3. 将this指向新创建的对象
    4. 执行构造函数中的代码，给新对象添加属性
    5. 如果构造函数返回了其他对象，那么这个对象作废，否则返回新创建的这个对象
54. xxx  is not a function   xxx不是一个方法，如果在一个对象上，说明这个对象上没有这个方法
55. 尝试了一下 path.resolve()  和path.join（） 感觉是一样的啊，都是找的此文件所在的绝对路径，暂时就这样吧，遇到的再看看其他情况
56. express的静态资源文件，app.use(express.static('public'));  这个的意思就是把public这个目录传递给了 `express.static`中间件函数，以便于访问， 就是这个意思  http://localhost:3000/images/kitten.jpg    http://localhost:3000/js/app.js
57. node的中间件  其实就是回调函数
58. webpack的样式兼容性处理时用的postcss-loader，需要一个postcss-preset-env的插件，这个插件会去找browserslist里面去找规则，browserslist在package.json里面
59. 设置node的环境变量要使用process.env.NODE_ENV='development' 或'production'
60. eslint设置下一行不生效   eslint-disable-next-line
61. webpack打包的入口形式可以有3种，最常见的就是string形式，单入口打包，最后也只会生成一个输出文件，另外一种时array的形式，这种就是多入口打包，但是还是只会生成一个输出文件，只有以object形式打包的才会有多个输出文件，object里面，有几对以key:value，就会生成几对输出文件，输出的bundle文件名就是key值，数组类型打包很少用，string和object形式用的很多
62. optimization一个作用是将node_module中的代码单独打包成一个chunk，就是把自己的代码和第三方的包分开，不然体积太大了，另一个作用是自动分析多入口chunk中，有没有公共的文件，如果有，就会单独打包成一个chunk，如果没有这个代码分割的话，比如在a.js和b.js里面都引入了jq，没有使用代码分割，就会在两个文件中都打包jq,使用分割只会，就会之打包出一个jq，不会重复打包
63. import动态引入的时候，可以控制引入的文件的名字，设置 /*webpackChunkName："xxxx" */就可以控制名字了
64. 懒加载，当文件需要使用时才加载，webpackPrefetch：true  预加载prefetch，会在使用之前，提前加载js文件
65. 正常加载可以认为是并行加载(同一时间加载多个文件)   ， 预加载：等其他资源加载完毕，浏览器空闲了，再偷偷加载资源
66. es6的class类，如果子想要扩展自己的方法，比如自己的方法里要打印自己的属性，那么在constructor那里就需要写this.xxx=xxx,因为super相当于是调用了父类的constructor，this是父类的
67. 构造函数的成员分为静态成员和实例成员，静态成员是直接通过构造函数.xxx=xxx来实现的，这种静态成员的访问只能通过构造函数.xx来访问，构造函数中的this.xxx=xxx，这种就是实例成员，只能通过新创建的实例来访问，就是实例.xxx
68. 构造函数继承：就是子构造函数里面用call来执行父构造函数这个方法，子构造函数就可以继承父构造的属性了，但是这种方法拿不到父构造函数原型上的方法，因为只是借用了构造函数，没有实现原型的继承，所有也就拿不到父构造函数原型上的方法了
69. 原型链继承，就是把子构造函数的原型指向父构造函数的实例，这样子构造函数的实例就能访问原型上面的属性和方法了，但是这样的话，会有引用值的问题，如果父构造函数的一个变量是一个引用类型，子构造函数的实例修改了这个值的话，那么子构造函数的任何实例的的这个属性都会被改变
70. 原型继承就是把子构造函数的原型指向父构造函数生成的实例对象，这样子构造函数的实例也能够继承父构造函数的方法了，这样也不会改变父构造函数的方法，如果把子构造函数的原型指向父构造函数的原型，那么就会改变父构造函数的方法，就是子类构造函数自己内部写了一个方法，但是由于直接指向了父构造函数的原型，这样的话，父构造函数里面也会有子构造函数的方法，所以才需要指向父构造函数生成的实例，而不是指向父构造函数的原型
71. 组合继承（伪经典继承）：就是原型链继承+构造函数继承的组合，这样就解决了引用值的问题，也能拿到父构造函数原型上的方法，但是有一个缺点，就是子构造函数的原型=父构造函数的实例时，这里父构造函数执行了一次，然后在子构造函数实例化的时候，又执行了一次父构造函数，所以执行了两次，相当于时子构造函数实例化的时候，把之前的那次执行给覆盖了，虽然结果是一样的
72. 经典继承就是把组合继承的原型链继承那里改成Object.create(父构造函数的原型)，这样就不会存在执行两次父构造函数了，不过这个是新的api,所以会有兼容问题
73. import是es6的语法，import 与 export/export default 搭配，实现导入导出，require是es6 ,node都有的语法，require与module.exports搭配，实现导入导出
74. 生成器函数调用需要调里面的next方法，才能执行生成器这个函数里面的代码
75. 用export default 暴露的时候，引入需要把暴露出来的default取一个别名再使用，也就是 import   { default as xxx} from 'xxx'，这种暴露有个简便的写法，直接import xx from 'xxx'，用的时候直接xxx.属性就行了
76. promise.race的使用场景：在发请求的时候，如果超时了，就执行对应的操作，成功了就执行成功的操作，就看谁快一点了
77. DNS查询过程：
    1. 首先搜索浏览器自身的DNS缓存，如果存在，则域名解析到此完成
    2. 如果浏览器自身的缓存里面没有找到对应的条目，那么会尝试读取操作系统的host文件，看是否存在对应的映射关系，如果存在，则域名解析到此完成
    3. 如果本地host文件不存在映射关系，则查找本地DNS服务器，（ISP服务器或者自己手动设置的服务器），如果存在，则域名解析到此结束
    4. 如果本地DNS服务器还没有找到的话，它就会向根服务器发出请求，进行递归查询
78. 浏览器缓存：浏览器缓存其实就是浏览器保存通过http获取的所有资源，是浏览器将网络资源储存在本地的一种行为
79. 强缓存：浏览器在加载资源时，会先根据本地缓存资源的header中的信息判断是否命中强缓存，如果命中，则直接使用缓存中的资源，不会再向服务器发送请求，这里的header是指 expires和cache-control
80. cache-control 是 http1.1 时出现的header信息，主要是利用该字段的 max-age来进行判断，它是一个相对时间，例如cache-control：max-age=3600  ，代表着资源的有效期是3600秒，cache-control除了该字段之外，还有几个常用的值
    - no-cache  需要进行协商缓存，发送请求到服务器确认是否使用缓存
    - no-store  禁止使用缓存，每一次都要重新发送请求
    - public  可以被所有的用户缓存，包括终端用户和CDN等中间代理服务器
    - private   只能被终端用户的浏览器缓存，不允许CDN等中间代理服务器对其缓存
    - cache-control与expires 可以在服务端配置时同时使用，同时使用的时候，cache-control优先级高
81. 协商缓存：当强缓存没有命中的时候，浏览器会发送一个请求到服务器，服务器根据header中的部分信息来判断是否命中缓存，如果命中，则返回304，告诉浏览器资源未更新，可使用本地的缓存，这里的header中的信息指的是 last-modify/if-modify-since和etag/if-none-match
82. 防抖：之前理解的不是很清楚，现在重新捋一下，防抖是单位时间内，只执行最后一次，代码层次解释：先定义timer，判断timer是否存在，如果存在，说明此时已经开启了一个定时器，这个时候就需要清空定时器，就是因为这个操作，所以就算疯狂的点击，也只有最后一次点击才是有效的，清空定时器之后再定义timer，再开启一个新的定时器
83. 节流：节流的原理是如果有定时器，就return，不阻止上一次的定时器，这样才能让一段时间内，固定频率的执行
84. iframe 系统之间通信，如果是嵌套的iframe，那么window.parent就是父页面，window.child就是嵌套的子页面，父页面给子页面发消息，window.child.postMessage(),子页面向父页面发消息，window.parent.postMessage(),如果当前页面监听到了其他页面的消息，要给发送消息的那个页面发消息，就是e.source.postMessage(),要注意勇iframe嵌套的时候，是否把iframe隐藏了，这里有些坑，比如隐藏的那个iframe里面的log打印展不开，请求也看不到响应
85. 如股在页面中要循环渲染echarts，那么此时要注意的就是init echarts的时候，需要勇refs来获取dom,而不是用id来获取，id获取的话，都只会获取到第一个id的dom.这样就有问题了，用refs就不会，因为每个组件都是独立的，就不会有这种问题
86. 怪异盒模型就是width包括content,padding,border，也就是设置border-box的时候，标准的盒模型就是width包括conent，想象一个盒子，里面就只有padding,border以及内容，就很清楚盒模型了
87. 文件上传就是用post，然后把header改成 'Content-Type': 'multipart/form-data'，上传的文件用FormData  const formData = new FormData();  formData.append('file', this.file);
88. vue2双向绑定原理：new Vue的时候，首先进行数据劫持，用Object.defineProperty将Vue里面的data数据劫持，然后进行解析，在解析的过程中，会有一个new Watcher的操作，这里就会把watcher加入到Dep的订阅里面，也就是在数据劫持的get的时候，在set的时候，Dep会通知Watcher去执行对应的update方法，两个函数作用：一个Watcher,自身有一个update方法，用来更新数据，一个Dep函数,Dep作用就是将Watcher加入到Dep的管理列表里面，并且在set的时候通知Watcher更新数据
