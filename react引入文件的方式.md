# 普通html引入和普通引入一样
# 脚手架引入
## 引入css
### require('./style.css') 可直接使用className作为类名 
### 或者import styles from './Category.css';应该使用以下方式：
#### 1.<div className={style.entry}>test </div>
    2.<div style={{marginTop:10}}>test </div>
    3.import ReactDOM from 'react-dom';
    <Button ref="button" />
    const button = ReactDOM.findDOMNode(this.refs.button);
    button.setAttribute('disabled', 'true'); 