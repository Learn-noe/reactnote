# redux
## action是指明用户的行为
## reducer用来把action和state一一对应，也就是触发了哪个actionstate将会做什么改变
## store用于存储reducer中的数据信息 它包括了完整的reducer
## dispatch用于在监听事件时派发action
### 1.action作用于store；
### 2.reducer根据store响应；
### 3.对于redux来说，store是唯一的；
### 4.store包括了完整的state；
### 5.state完全可预测

# react-redux
## action 是行为的抽象，是最普通的函数，它里面有一个type属性，还有一个集体的行为，也就是数据将要改变的方法
## reducer是响应的抽象，他传入原始的状态，和将要进行的行为（action）,只有触发行为之后才会残生新的状态，也就是reducer的返回值
## reducer事实上是一个对象 function counter(state,action){
    //判断是否存在状态 如果不存在则返回0
    if(typeof==='undifined'){
        return 0
    }
    //用来定义action类型和将要产生的状态改变方式
    switch(action.type){
        case:'INCREMENT';
            //集体的改变方式
            return state+1
        case:'DECREMENT':
            return state-1;
        //默认状态
        default:
            return state
    }
}
## store可看作是一个仓库，可以用createStore方法传入reducer来的到store,一个应用对应一个store
### var store=Redux.createStore(counter) counter是上面定义的一个reducer对象
## 获取将要进行操作的dom元素
### var valueE1=document.getElementById('value')
## function render(){
    //吧store仓库里的reducer写进将要操作的dom里面
    valueE1,innerHTML=store.getState.toString()
}
### render()
### store的subscribe方法监听state变化，一旦变化就执行render函数,也就是对应的改变valueE1里面的数据
### store.subscribe(render)
##  /*----store的dispatch定义一个操作信息，reducer会将这个信息匹配具体对state的操作*/ 视图层操作 用来监听事件通过dispatch派发action行为，以数据做出相应的更新
   document.getElementById('increment')
     .addEventListener('click', function () {
       store.dispatch({ type: 'INCREMENT' })
     })

   document.getElementById('decrement')
     .addEventListener('click', function () {
       store.dispatch({ type: 'DECREMENT' })
     }) 
## 其他需要了解的方法：
### applyMiddlewares():传入中间件，并将其依次执行
### connect: 连接容器组件和UI组件
const VisibleTodoList = connect(  
       mapStateToProps,  //建立一个从外部state到UI组件props的映射
       mapDispatchToProps  //定义UI组件的参数到dispatch方法的映射
)(TodoList)  
//TodoList是 UI 组件，VisibleTodoList就是由 React-Redux 通过connect方法自动生成的容器组件 其实容器组件也是相对应自己创建的
### 具体的connect mapStateToProps mapDispatchToProps请参考https://blog.csdn.net/q1056843325/article/details/54880804
## Provider
## Provider组件让我们省了不少功夫 
### 它就相当于我们整体的容器组件（不过区别很大） 
### 用法就是在我们根组件外部嵌套一层Provider，传入store 
### （使用全局的store有风险） 
### v这样所以的子组件都可以开心地拿到state了 
### 我们也省心了
render(
  <Provider store={store}>
    <App/>
  </Provider>,
  document.getElementById('root')
);
## 内部的原理是： 
### Provider接受store作为其props，并声明为context的属性之一 
### 子组件在声明了contextTypes之后可以通过this.context.store访问到store
### 原理可参考：http://react-china.org/t/react-redux/9072/23;
### https://www.cnblogs.com/heigehe/articles/6237362.html