- Vuex工作流
    1. 组件 -> dispatch -> action
    2. dispatch -> type(actionType) -> 某一个action
    3. action -> commit 调用 -> mutation
    4. mutation -> change -> state
    5. render
- 文件集合
    1. actionTypes action类型
    2. actions     调用mutation方法
    3. mutations   更改state方法
    4. state       中央数据
    5. store


# 组件划分
 - TodoList
    1. TodoInput
    2. TodoList
     - TodoItem
        1. 完成或未完成的选择
        2. 删除该项
        3. 正在做的按钮