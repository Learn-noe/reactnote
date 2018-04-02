# redux是什么？
### redux是一个数据状态管理插件，搭配React非常合适
# 使用场景
### 无论是移动端还是pc端，当你使用React或者vue开发组件化的spa时，组件之间的共享信息是一个非常大的问题，例如，用户登陆后客户端会存储用户信息（如userId,头像等），而系统的很多组件都会用到这些信息，例如收藏，点赞，评论等。这些组件在用到用户信息时，不会再获取一边，因此没个系统都需要一个管理多组件使用的公共信息的功能，这就是Redux的作用。
# 安装redux依赖 npm install redux --save  npm install react-redux --save
# 基本使用 
## export default function(){
    //定义改变状态的规则的一个函数，即reducer他有两个函数 state和action
    function counter(state=0,action){ //默认参数
        switch(action.type){
            //具体的action类型行为
            case 'INCREMENT':
                //具体要改变的状态
                return state+1
            case:'DEAREMENT':
                return state-1
            default:
                默认下的原始状态
                return state
        }
    }
    //根据规则生成一个相对应的store存储该reducer里面的行为和改变之后的状态，事实上store可以看作是一个变量。
    let store=createStore(counter)
    //定义数据（即state）发生变化之后该如何派发行为 用subscribe进行监听
    store.subscribe(()=>{
        console.log('fn1->curent state',store.getState())
    })
    store.subscribe(()=>{
        console.log('fn2->curent state',store.getState())
    })
    //根据store(reducer)的变化出发行为 用dispatch进行派发
    store.dispatch({type:'INCREMENT'}) 事实上 是向store派发一个action的行为类型，代表了action具体的行为
    store.dispatch({type:'INCREMENT'})
    store.dispatch({type:'DECREMENT'})
}
    