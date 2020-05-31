# 操作HTML页面

- 选中这个标签

  ```html
  <div id="goudan">123456</div>
  <script>
  	document.getElementById("goudan");
  </script>
  ```

- 操作内容（添加一些文字）

  ```js
  document.getElementById("goudan").innerHTML = "Hell wrode!";
  ```

- 解析标签

  ```js
  document.getElementById("goudan").innerText = "<div>Hell wrode!</div>";
  ```

- 不解析标签

  ```js
  document.getElementById("goudan").innerText = "<div>Hell wrode!</div>";
  ```

- 读写操作

  ```js
  //先读取，后打印日志
  console.log(
  	document.getElementById("goudan").innerHTML
  );
  //先写入内容，读取后再打印日志
  document.getElementById("goudan").innerHTML = "789456";
  console.log(
  	document.getElementById("goudan").innerHTML
  );
  ```

  