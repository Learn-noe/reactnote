## 文件夹action 里面放的是action文件  
### userinfo.js 他事实上就是一个定义了很多相对应action的文件
    import * as actionTypes from '../costants/userinfo'
    
    export function login(data){
        return{
            type:actionTypes.USERINFO_LOGIN,
            data
        }
    }
    export function updateCityName(data){
        return{
            type:actionTypes.UPDATE_CITYNAME,
            data
        }
    }
### 
## 文件夹 reducers  里面都是定义的reducer文件
### 第一步：定义reducer  index.js //reducer出口文件  包装的文件
    inport {combineReducers} from 'redux'
    import userinfo from './userinfo'
    
    const rootReducer=combineReducers({
        userinfo
    ]})
    export default rootReducer
### userinfo.js userinfo就是一个定义的reducer
     
     import * as actionTypes from '../consttants/userinfo'
     const initialState={}
     
     export default function userinfo(state=initialState,action){ //state=initialState是默认参数
        switch(action.type){
            //实现登陆的action行为类型
            case actionTypes.USERINFO_LOGIN:
                return action.data
                
            //修改城市的action行为
            case actionTypes.UPDATE_CITYNAME:
                return action.data
            
            default:
                return state
        }
     }
## 文件夹 contants 里面放的是生成的文件（自定义的文件根据reducer而来的）
### 第二部：定义常量 userinfo.js
    //定义常量
    export const USERINFO_LOGIN='USERINFO_LOGIN'
    export const UPDATE_CITYNAME='UPDATE_CITYNAME'
## 文件夹store  生成的store文件
### 第三步：生成store store.js
    import {createStore} from 'redux'
    import rootReducer from '../reducers' //引用redyucer
    
    export default function configureStore(initialState){ //rootReducer是一个总的规则，即reducer的包装文件
        const store=createStore(rootReducer,initialState,
            window.devtoolsExtension?window.devToolsExtension()：undefined  //他是chrome浏览器的状态测试工具
        )
        return store
    }
## 入口文件
### index.js
    import React from 'react'
    import {render} from 'react-dom'
    import {Provider} from 'react-redux'
    import configure from './store/configureStore'
    
    import Hello from './containers/hello'
    
    const store=configureStore()
    
    render(
        <Provider store={store]> //最外层的容器  react-redux自身规定的
            <Hello/>
        </Provider>,
        document.getElemntById('root')
    )
    
## 第四步：文件夹 containers 里面是生成的文件
### hello.js
    import React from 'react'
    import {connect} from 'react-redux'
    import {bineActionCreators} from 'redux'
    
    import * as userinfo Actions from '../actions/userinfo'
    import A from '../components/A'
    import B from '../components/B'
    import C from '../components/C'
    
    class Hello extends React.component{
        render(){
            return(
                <div>
                    <p>hello world</p>
                    <hr/>
                    <A userinfo={this.props.userinfo} />
                    <hr/>
                    <B userinfo={this.props.userinfo} />
                    <hr/>
                    <C actions={this.props.userinfo} />
                </div>
            )
        }
        componentDidMount(){
            //模拟登陆
            this.props.userinfoActions.login({ login是actionas里定义的方法
                userid:'abc',
                city:'beijing'
            })
        }
    }
    
    function mapStateToProps(state){ //
        return{
            userinfo:state.userinfo //他是reducer index.js文件中生成的state
        }
    //用于触发数据行为以及监听发生的变化
    function mapDispatchToProps(dispatch){
        return {userinfoActions:bindActionCreators(userinfoActions,dispatch)
        }
    }
    export default connect( //进行封装 connect 
        mapStateToProps,   
        mapDispatchToProps
    )(Hello)
## components文件夹   header文件夹
### A.js
    import React from 'react'
    
    export default class A extends React.Component{
        render(){
            return(
                <p>{this.props.userinfo.userid}</p>
            )
        }
    }
###  B.js
    import React from 'react'
    
    export default class B extends React.Component{
        render(){
            return(
                <p>{this.props.userinfo.userid}</p>
            )
        }
    }
### C.js
    import React from 'react'
    
    export default class C extends React.Component{
        render(){
            return(
                 <div>
                    <button onClick={this.changeUserInfo.bind(this)}>修改</button>
                 </div>   
            )
        }
        changeUserinfo(){
            const actions=this.props.actions
            actions.login({
                userid:'123',
                city:'beijing'
            })
        }
    }
## redux 
### sction ->store <-reducer 
### 关系：1.调用store.dispatch(action) 将action传给store
         2.store调用传入的reducer函数。store把当前的state树 和action 传给reducer
         3.根据reducer吧多个子reducer合并为一个state树输出
         4.store保存了根reducer返回完整的state树 图解请参考：https://www.cnblogs.com/shuiyi/p/5081250.html
    