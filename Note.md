# 原型及原型链 
 [原型对象](https://blog.csdn.net/ylwdi/article/details/82805255)
 ## 1.1函数的原型对象
 
 在JavaScript中，我们创建一个函数A(就是声明一个函数), 那么浏览器就会在内存中创建一个对象B，而且每个函数都默认会有一个属性 prototype 指向了这个对象( 即：prototype的属性的值是这个对象 )。这个对象B就是函数A的原型对象，简称函数的原型。这个原型对象B 默认会有一个属性 constructor 指向了这个函数A ( 意思就是说：constructor属性的值是函数A )。
```
<body>
    <script type="text/javascript">
        /*
            声明一个函数，则这个函数默认会有一个属性叫 prototype 。而且浏览器会自动按照一定的规则
            创建一个对象，这个对象就是这个函数的原型对象，prototype属性指向这个原型对象。这个原型对象
            有一个属性叫constructor 执行了这个函数
            注意：原型对象默认只有属性：constructor。其他都是从Object继承而来，暂且不用考虑。
        */
        function Person () {
 
        }       
    </script>
</body>

```
## 1.2 使用构造函数创建对象
当把一个函数作为构造函数 (理论上任何函数都可以作为构造函数) 使用new创建对象的时候，那么这个对象就会存在一个默认的不可见的属性，来指向了构造函数的原型对象。 这个不可见的属性我们一般用 [[prototype]] 来表示，只是这个属性没有办法直接访问到。
```
<body>
    <script type="text/javascript">
        function Person () {
 
        }   
        /*
            利用构造函数创建一个对象，则这个对象会自动添加一个不可见的属性 [[prototype]], 而且这个属性
            指向了构造函数的原型对象。
        */
        var p1 = new Person();
    </script>
</body>
```

