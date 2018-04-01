## 具体请参考 https://www.jianshu.com/p/e3adc9b5f75c，详细讲解以后补上 
## 下载安装react-router  npm install --save-dev react-router react-router-dom

### export default class App extends React.Component{
    render(){
        return(
            <div>{this.props.child  }</div>
        )
    
    }
}

## 首页配置
###  class Home extends React.Component{
            render(){
                return(
                    <div>
                        <p>Home</p>
                        //设置跳转的页面 html跳转方式
                        <Link to="/list">to list</List
                    </div>
                    )
            }
    }
    export default Home
    
    
### class List extends React.Component{
        render(){
            const arr=[1,2,3]
            return(
                <ul>
                    {arr.map((item,index)=>{
                        return <li key={index} onclick={this.onclick} />
                    })}
                </ul>
            )
        }
        clickHandler(value){
            //js跳转方式
            hashHistory.push('/detail/'+value)
            或者 hashHistory.push('/detail/1/2')
        }
}
export default List

## 页面返回   history.back()

### 获取参数 class Dtail extends React.Component{
        render(){
            return (
                <p>Detail ,url参数：{this.props.paramms.id}
            )
        }
}
export default Detail

### RouteMap
    export default class RouteMap extends React.Component{
        updateHandle(){
            console.log('每次router之后都会触发')
    render(){
        return(
            <Router history={this.props.history} onUpdate={this.updateHandle}>
                <Route path='/' component={App}>
                    <IndexRoute component={Home}/>
                    <Route path='List' component={List}/>
                    <Route path='Detail/:id/:type'component={Detial} />
                    <Route path="*" component={NotFound}>
                </Route>
            </Router>
        )
    }
        }
    }
    
    --Huge-app 首页先加载