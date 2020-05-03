# 操作class名字

## 操作class名字的方法

- 添加class名字

  ```js
  var oBox = document.getElementById("box");
  oBox.classList.add("yanxin");
  ```

- 添加多个class名字

  ```js
  var oBox = document.getElementById("box");
  oBox.classList.add("yanxin","goudan");
  //多个类名用逗号隔开
  ```

- 移除class名字

  ```js
  var oBox = document.getElementById("box");
  oBox.classList.remove("afei");
  ```

- 移除多个class名字

  ```js
  var oBox = document.getElementById("box");
  oBox.classList.remove("afei","yanxin");
  ```

- 切换class名字

  ```js
  var oBox = document.getElementById("box");
  oBox.classList.toggle("afei");
  //特点：如果这个名字已经存在就直接删除，如果这个名字不存在，就直接添加
  ```

- 切换class多个名字

  ```js
  var oBox = document.getElementById("box");
  oBox.classList.toggle("afei","yanxin");
  ```

- 读取单个class名字

  ```js
  var oBox = document.getElementById("box");
  console.log(oBox.classList[0]);
  console.log(oBox.classList[1]);
  ```

- 读取所有class名字

  ```js
  var oBox = document.getElementById("box");
  console.log(oBox.className);
  ```

  