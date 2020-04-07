## HTML

### 表单元素

#### 作用：收集用户数据

#### input标签

- type属性：输入框类型 
  取值：

- - text：普通文本框
  - password：密码框，输入内容显示成小圆点
  - number：数字输入框
  - checkbox：多选框  **加name属性**  默认选中：**checked**
  - radio：单选框  **加name属性**在指定多个单选框中选

- value属性：输入框的原有值
-  input元素可以制作按钮 （button）
  当type值为reset、button、submit时，input表示按钮 

#### select标签

 下拉列表选择框 

```
<select>      <!-- selected布尔属性表示默认选中 -->
    <option selected>选项1</option>
    <option>选项2</option>
    ...
    ...
</select>
```

#### textarea标签

 文本域，多行文本框 

