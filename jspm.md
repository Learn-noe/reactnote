## module模块写法 

### 1.AMD

### 2.CommenJs

### 3.Es6

## Jspm支持所有模块 他是一个包管理工具 他可以使用Traceur,babel实时编译  可以优化创建打包
### 安装jspm   npm install -g jspm
### 创建文件夹  mldir 文件夹 &&cd 文件夹
### npm install jspm --save-dev创建依赖文件
### jspm init 配置jspm

### 下载react和react-dom依赖
    jspm install react
    jspm install react-dom
### 安装sementic-ui
    jspm install semantic-ui
### 安装browser-sync
    npm install -g browser-sync
### 创建服务器监视文件的变化
    browser-sync start --server --no-notify --file 'index.html ,app/**/*.js'
### 创建Comment组件 放到CommentList里，CommentList作为父组件，回作为Comment的子组件，this.props
### 安装react-router
    jspm install react-router@版本
### jspm配置
    jspm install jquery github : compnets/jquery
    jspm install css npm css