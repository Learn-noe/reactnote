# react获取数据的四种方式
## ajax() $.ajax() fetch() axios()
## ajax()
### class Nav extends React.Component{
###   construtor(){
###       super();
###       this.state={
###          arr:{}
###       this.get=this.get.bind(this);
###        };
###    get(){
###       ajax('./data/data.json',function(res){
###          var json=new Function(){return res}
###             console.log(data)
###        })
###       }
###      }
###    }
## $.ajax()
### class Nav extends React.Component{
###   construtor(){
###       super();
###       this.state={
###          arr:{}
###       this.get=this.get.bind(this);
###        };
###    get(){
###       $.ajax({
###               type:'get',
###                url:
###                success:function(res){
###                console.log(res)
###               }
###          })
## fetch()
### class Nav extends React.Component{
###   construtor(){
###       super();
###       this.state={
###          arr:{}
###       this.get=this.get.bind(this);
###        };
###    get(){
###            fetch('data/word.txt').then(res)=>{if(res.ok){
###                res.text().then((data)=>{console.log(data)}).catch((res)=>{console.log(res)}
###            }}
###      }
## axios()
### class Nav extends React.Component{
###   construtor(){
###       super();
###       this.state={
###          arr:{}
###       this.get=this.get.bind(this);
###        };
###    get(){
###           axios.get('url').then((res)=>{console.log(res.data[i])}).catch((err)=>{console.log(err.status)})
###   }

