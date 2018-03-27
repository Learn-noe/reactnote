# redux
## action是指明用户的行为
## reducer用来把action和state一一对应，也就是触发了哪个actionstate将会做什么改变
## store用于存储reducer中的数据信息 它包括了完整的reducer
## dispatch用于在监听事件时派发action
### 1.action作用于store；
### 2.reducer根据store响应；
### 3.对于redux来说，store是唯一的；
### 4.store包括了完整的state；
### 5.state完全可预测