#### 三、路由的基本使用

- 明确好界面中的导航区，展示区
- 导航区的a标签改为Link标签    

```jsx
<Link to='/xxx'>Home</Link>
```

- 展示区写Route标签进行路径的匹配

```jsx
<Route path='/xxxx' component={Home}/>
```

- <App>的最外侧包裹了一个<BrowserRouter>或<HashRouter>

#### 四、路由组件与一般组件

- 写法不同

   一般组件： <Demo/>

  路由组件：<Route path='/demo' component={Demo}/>

- 存放位置不同

  一般组件：components

  路由组件：pages

- 接收到的props不同

  一般组件：写组件标签时传递了什么，就能收到什么

  路由组件：接收到三个固定的属性

    history:

  ​           go: f go(n)

  ​           goBack: f goBack()

  ​           goForward: f goForward()

  ​           push: f push(path,state)

  ​           replace: f replace(path,state)

  location:

  ​             pathname: "/about"

  ​             search: "

​                    state: undefined

​        match:

​                    params: {} 

​                    path: "/about"

​                     url: "/about"

#### 五、NavLink与封装NavLink

- NavLink可以实现路由链接的高亮，通过activeClassName指定样式名，自定义更改颜色，要注意权值问题 
- 标签体内容是一个特殊的标签属性
- 通过this.props.children可以获取标签体内容

#### 六、Switch的使用

- 通常情况下，path和component是一一对应的关系
- Switch可以提高路由匹配效率（单一匹配）

#### 七、解决多级路径刷新页面样式丢失的问题

- public/index.html中引入样式时不写 ./ 写 / (常用)
- public/index.html中引入样式时不写 ./ 写 %PUBLIC_URL%(常用)    只适用react脚手架
- 使用HashRouter

#### 八、路由的严格匹配与模糊匹配

- 默认使用的是模糊匹配（简单记：输入的路径必须包含要匹配的路径，且顺序要一致
- 开启严格匹配： <Route exact={true} path="/about" component={About} />
- 严格匹配不要随便开启，需要再开，有些时候开启会导致无法继续匹配二级路由

#### 九、Redirect的使用

- 一般卸载所有路由注册的最下方，当所有路由都无法匹配时，跳转到Redirect指定的路由

- 具体编码

  ```
  <Switch>
   <Route path="/about" component={About}/>
   <Route path="/Home" component={Home}/>
   <Redirect to="/about">
  </Switch>
  ```

  