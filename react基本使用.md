# react
## react是组件和状态的集合
## react通过this.props传递数据这是父->传递 子->父传递可通过 子组件需要控制自己的 state， 然后告诉父组件自己的state，通过props调用父组件中用来控制state的函数，在父组件中展示子组件的state变化。
## state状态只能通过this.setState({title: 'React'});来改变 state的更新是异步的
#  State 与 Props 区别
## 除了State, 组件的Props也是和组件的UI有关的。他们之间的主要区别是：State是可变的，是组件内部维护的一组用于反映组件UI变化的状态集合；而Props对于使用它的组件来说，是只读的，要想修改Props，只能通过该组件的父组件修改。在组件状态上移的场景中，父组件正是通过子组件的Props, 传递给子组件其所需要的状态。
## state状态的类型是数组
### // 方法一：将state先赋值给另外的变量，然后使用concat创建新数组 当向books中增加一本书时，使用数组的concat方法或ES6的数组扩展语法
        var books = this.state.books; 
        this.setState({
          books: books.concat(['React Guide']);
        })

        // 方法二：使用preState、concat创建新数组
        this.setState(preState => ({
          books: preState.books.concat(['React Guide']);
        }))

        // 方法三：ES6 spread syntax
        this.setState(preState => ({
          books: [...preState.books, 'React Guide'];
        }))
### 当从books中截取部分元素作为新状态时，使用数组的slice方法：
        // 方法一：将state先赋值给另外的变量，然后使用slice创建新数组
        var books = this.state.books; 
        this.setState({
          books: books.slice(1,3);
        })

        // 方法二：使用preState、slice创建新数组
        this.setState(preState => ({
          books: preState.books.slice(1,3);
        }))
### 当从books中过滤部分元素后，作为新状态时，使用数组的filter方法：
    // 方法一：将state先赋值给另外的变量，然后使用filter创建新数组
    var books = this.state.books; 
    this.setState({
      books: books.filter(item => {
        return item != 'React'; 
      });
    })

    // 方法二：使用preState、filter创建新数组
    this.setState(preState => ({
      books: preState.books.filter(item => {
        return item != 'React'; 
      });
    }))
## 状态的类型是普通对象（不包含字符串、数组）
### 使用ES6 的Object.assgin方法
    // 方法一：将state先赋值给另外的变量，然后使用Object.assign创建新对象
    var owner = this.state.owner;
    this.setState({
      owner: Object.assign({}, owner, {name: 'Jason'});
    })

    // 方法二：使用preState、Object.assign创建新对象
    this.setState(preState => ({
      owner: Object.assign({}, preState.owner, {name: 'Jason'});
    }))
### 使用对象扩展语法（object spread properties）
    // 方法一：将state先赋值给另外的变量，然后使用对象扩展语法创建新对象
    var owner = this.state.owner;
    this.setState({
      owner: {...owner, name: 'Jason'};
    })

    // 方法二：使用preState、对象扩展语法创建新对象
    this.setState(preState => ({
      owner: {...preState.owner, name: 'Jason'};
    }))
    
## 具体请参考https://www.jianshu.com/p/c6257cbef1b1

## 可通过ref传递属性  和js中的属性传递差不多


