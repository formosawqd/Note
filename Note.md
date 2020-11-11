##### 前端模块化：为了更好的处理得到想要的数据，将数据放在一个js文件里，commonJS是把这个js文件导出，在这个js文件里用module.exports来导出。在想要引用的地方用require来引入，在require的时候还可以结构出来
##### 箭头函数的this指向，指向定义时的执行上下文，或者就是指向外层代码执行上下文
##### 数组去重的set用法： let arr = [1, 2, 3, 4, 6, 3, 6, 7,7, 7, 2, 45, 6];       let newArr = new Set(arr)  得到结果[1, 2,  3, 4, 6, 7, 45]  
##### let o = "formosa";  console.log(Object.prototype.toString.bind(o)());  打印结果：[object String] bind只能改变this,不会执行，如果换成call,apply就可以省略后面的括号
