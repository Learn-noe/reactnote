# React生命周期 可参考 http://blog.csdn.net/limm33/article/details/50942808  http://react-china.org/t/react/1740 http://blog.csdn.net/u010945409/article/details/72874601
## React生命周期分为三个阶段 实例化阶段、存在期阶段、销毁阶段（存在其阶段可以反复执行）
## 1.组件实例化阶段（只会执行一次）
###  constructor
### componentWillMount
### render
### componentDidMount
## 2.组件存在期 （在存在期阶段，每重新渲染一次，都会执行一遍）
### coponentWillReceiveProps
### shouldComponentUpdate (如果返回false则不会重新渲染，也会跳过render前后的钩子函数)
### componentWillUpdate
### render
### componentWillUpdate （渲染之后，可以通过ref或者findDOMNode，来操作DOM，当React运行在服务端是，不会被调用） 
## 3.组件销毁阶段
### componentWillUnmount
# React的数据流是单向的 
## props：很好理解，就是向组件本身传递的参数。 
## 你可以通过props对组件进行状态化处理，可以通过PropTypes(接受一个对象最为参数)进行参数验证
## static propTypes={
##    data:PropTypes.shape({
##      id:PropTypes.string,
##      .......
##  }).isRequired
## }
# 如果没有传进参数过来怎么办？使用defaultProps设置默认值
## static defaultProps={
##    name:'No one'
## }
# 注意： 
##   1、尽量props当作数据源，不要修改数据，作为只读数据，与子组件进行通信（包括数据和事件） 
##   2、state存储简单的视图状态，在你setstate之后，你是获取不到state的值，state值的改变是在render之后才会改变，如果你要向父组件传递state的数据，那么componentDidMount中传递数##  据，或者通过setstate（{state:’ss’},()=>{回调函数}）实现，( 原因：setstate本质上是异步的。。。。。。jb)state尽量不要保存计算后的值，state可以接受一个函数，返回值为对象即可
## this.setstate((state)=>{
##    return {state:'..'}
## });
