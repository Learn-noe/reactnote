# react
## react是什么？
### React是一个声明式的，高效的，并且灵活的用于构建用户界面的 JavaScript 库。
## react基本声明形式？
### class ShoppingList extends React.Component {
      render() {
        return (
          <div className="shopping-list">
            <h1>Shopping List for {this.props.name}</h1>
            <ul>
              <li>Instagram</li>
              <li>WhatsApp</li>
              <li>Oculus</li>
            </ul>
          </div>
        );
      }
    }
// Example usage: <ShoppingList name="Mark" />
    export default ShoppingList;
或者 export default class ShoppingList extends React.Component {
      render() {
        return (
          <div className="shopping-list">
            <h1>Shopping List for {this.props.name}</h1>
            <ul>
              <li>Instagram</li>
              <li>WhatsApp</li>
              <li>Oculus</li>
            </ul>
          </div>
        );
      }
    }
### ShoppingList是一个声明的React组件类 组件接收参数，成为props(属性)，并通过render方法return一个ui结构层次,事实上就是一个html页面形式，只不过把html中的class属性改成了className
### 在这里<div /> 语法在构建时被转换为 React.createElement('div')。上面的例子等价于：return React.createElement('div', {className: 'shopping-list'},
  React.createElement('h1', /* ... h1 children ... */),
  React.createElement('ul', /* ... ul children ... */)
); 这就是jsx语法