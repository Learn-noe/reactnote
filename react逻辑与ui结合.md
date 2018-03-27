## 可以吧react组件当一个组件来用
## 底层的逻辑处理过程
## 把原有的dom的数据结构与react结合起来
### var destination=document.queryselector('#container');
### var Circle=React.createClass({
###     render:function(){
###         var circleStyle={
###             padding:10,
###             margin:20,
###             display:"inline-block",
###             backgroundCorlor:this.props.bgColor,
###             border-Radius:"50%"，
###             width:100,
###             height:100
###             
###             };
             render(
###             <div style={circleStyle}>
                
</div>
)
            }
        });
        var theCircle=<Circle bgCorlor="#f9d240"/>;
        原型的颜色随意变换 返回原型组件
        function showCircle(){
            var colors=['blue','green','yellow','red','skeyblue','#h8j7h5','#ff8052','#a401441'];
            var renderDara=[];
            for (var i=0;=<colors.length;i++){
                var ran=Math.floor(Math.random()*colors.length);
<!--                //确保key值是唯一的-->
                renderData.push(<Circle key={i+colors[ran]} bgColor={colors[ran]}/>)
            }
<!--
            var ran=Math.floor(Math.random()*colors.length);
            return <Circle bgColor={color[ran]}/>
-->
            return renderData;
        }
        ReactDOM.render(
            <div>
                {showCircle()} 
<!--
                {showCircle()} 
                {showCircle()}
-->
<!--
                {theCircle} 等同于下面的组件
                //jsxx对象  可以当做一个变量来实现 
                <Ciecle bgCorlor="#f9d240" />
-->
</div>,destination
        );
