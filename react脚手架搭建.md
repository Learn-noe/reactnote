### 安装create-react-app 缺点webpack写进node——modules里不容易配置
#### cnpm install create-react-app -g
### 搭建项目工作目录
### 运行create-react-app reactdemo 生成reactdemo项目文件夹 （注意：reactdemo可以加-不能大写）
#### create-react-app有点
##### 无需配置：配置堪称完美，几乎不会在配置其他东西，就可以上手项目
##### 高集成性：集成了react,jsx,Es6和flow的基本功能
##### 自带服务：集成了开发服务器，你可以实现开发预览一体化。
##### 热更新：保存自动更新，让你的开发更简单。
##### 全兼容性：自动处理CSS的兼容问题，无需添加-webkit前缀。
##### 自动发布：集成好了发布成品功能，编译后直接发布，并且包含了sourcemaps功能。

### 项目文件夹
### public放一些图片文件
### src里放置我哦们的组件逻辑布局信息

## 第二种创建react脚手架项目的方法 它需要yeomen支持 他是谷歌和其他开发这一期开发的 
### 安装yeomen cnpm install -g yo(yeomen简写)
### 安装cnpm install -g generator-eract-webpack
### 创建项目文件夹 mkdir my-react 进入目录
### 运行yo react-webpack创建文件目录
### yeomen脚手架优点：
#### 基于webpack脚手架搭建环境目录，可以根据自己的需要配置自己需要的webpack
#### 支持Es66,集成了Babel-Loader
#### 支持不同风格的css(sass,less,stylus)
#### 集成了ESlint功能
#### 可以轻松的配置单元测试，比如Karma?和Mocha
## 第三种方法 react+webpack构建
### 创建文件夹 运行npm init 生成package.json
### cnpm install --save-dev 生产环境中使用
### 根目录新建webpack.config.js
#### const path=require('path');
#### module.exports={
####    entry:'./app/index,js',
####    output:{
####        filename:'index.js',
####        path:path.resolve(__diename,'dist'),
####        //实现自动刷新实时预览
####        public:'temp/'
####    },
#### devServer:{
####   contentBase:'./',
####    host:'localhost',
####    compress:true,
####    port:1717
#### }
#### }
### 在根目录创建app/index文件夹
### 根目录下创建index.html
### 安装webpack服务器 cnpm install --save-dev webpack-dev-server
## 配置package.json
### scrips里
#### "scrips":{
####   "build":"webpack",
####    "server":"webpack-dev-server --open"
#### }
#### 运行npm run server
## 配置babel
### 安装babel 运行命令

#### cnpm install --save-dev babel-core babel-loader babel-preset-es2015 babel-preset-react

## 配置module
### module:{
###    loaders:[
###     {
###            test:/\.js$/,
###             //node_module不参与编译
###            exclude:/node_modules/,
###            loaders:"babel-loader",
###            query:{
###             presets:['es2015','react']
###         }
###        },{
                testL/\.css/,
                loader:['style-loader','css-loader']
}
###    ]
### }
## 安装react react-dom包
### cnpm install --save-dev react react-dom
## app/index里写react组件

## react路由
### 安装路由包 cnpm install --save react-router react-router-dom
## import {BrowserRouter as Router,Route} from 'react-route';
### <Router>
        <div>
            <Route exact path="/" component={Home}/>
            <Route  path="/index" component={index}/>
            <Route  path="/" component={Home}/>


        </div>
###  <Router />
### import React from 'react';
### import {NavLink} from 'react-router-dom';
### const NavBar =()=>(
        <div>
            //精确匹配
            <NavLink exact to="/">Home</NavLink>
            <NavLink exact to="/index" .activeClassName="">index</NavLink>
            <NavLink exact to="/about">About</NavLink>
        </div>
### )
### import {BrowerRouter as Router,route,Redirect} from 'react-route';
### <Router>
        <div>
            <Nav />
            <Switch>
                <Route exact path="/" component={Home}/>
                <Route  path="/index" component={index}/>
                <Route  path="/Home/:param/:aaa" component={Home}/>
                <Redirect from="/redireact" to="Home">
                <Route  component={404页面}/>
            <Switch>
            


        </div>
###  <Router />
## promit标签 弹出一个提示框避免无意识提交
### import{Prompt} from 'eract-router-dom
### 写在组件里面 
### <Prompt message="提示：是否离开" when={this.state.power}> 在构造函数里面设置this.state={power:false }
### when是一个开关


### export default NavBar
## 安装loader包 npm install --save-dev style-loader css-loader