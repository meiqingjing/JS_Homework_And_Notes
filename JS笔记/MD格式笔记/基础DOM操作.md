# 基础DOM操作

## 获取HTML元素的方式（标签/元素/节点）

- 通过ID获取

  ```js
  document.getElementById("godan");
  ```

- 通过class获取

  ```js
  //不兼容IE8及以下
  document.getElementsByClassName("warp");
  ```

- 通过标签名获取

  ```js
  document.getElementsByTagName("div");
  ```

- 通过选择器

  ```js
  document.querySelector("#goudan .warp");//单个获取
  document.querySelectorAll();//多个获取
  ```

- 通过name属性获取

```js
//极为少用，一般在表单里面使用
document.getElementsByName();
```

## 获取元素详解

- 通过ID获取

  ```html
  <div id="nav"></div>
  <p class="goudan">123456</p>
  <p class="goudan">123456</p>
  <p class="goudan">123456</p>
  <script>
  	var oNav = document.getElementById("nav");
      //只能获取单个元素节点
  </script>
  ```

- 通过ClassName获取

  ```html
  <div id="nav"></div>
  <p class="goudan">123456</p>
  <p class="goudan">123456</p>
  <p class="goudan">123456</p>
  <script>
  	var x = document.getElementsByClassName("goudan");
      //获取到的是一个集合（不管获取的是一个还是多个，得到结果都是一个集合）
      console.dir(oNav);
      //打印结果：oNav存储的是一个单个节点对象
      console.log(x);
      //打印结果：x存储的是一个数组结构，这个数组结构里面存放了多个节点。
      oNav.innerText = "刷机大师客单价快点结束";
      //可以直接对节点对象进行点操作。
  	x[0].innerText = "刷机大师客单价快点结束";
      //必须先把数组结构里的节点对象拿出来(跟数组一样使用下标获取)，再进行点操作。
  </script>
  ```

- 通过TagName获取

  ```html
  <div>
      <p></p>
      <p></p>
      <p></p>
  </div>
  <script>
  	var aP = document.getElementsByTagName("p");
      //获取到的也是一个集合
      console.log(aP);
      aP[1].innerText = "xxxxxxx";
      //第二个P标签添加内容也是需要通过下标拿到元素节点后再进行点操作。
  </script>
  ```

- 通过选择器获取

  ```html
  <div id="main">
      <p></p>
      <p></p>
      <p></p>
  </div>
  <script>
      //这样需要两次获取比较麻烦
  	var oMain = document.getElementById("main");
      var aP = oMain.document.getElementsByTagName("p");
      
      
      //获取该选择器对应的所有标签
  	var aP = document.querySelectorAll("#main p");
      //获取该选择器对应的第一个标签
      var x = document.querySelector("#main p");
  </script>
  ```

## DOM事件

- onclick——鼠标点击事件

  ```html
  <div id="main"></div>
  <script>
  	var oM = document.getElementById("main");
      // 节点 . 事件 = 执行函数
      oM.onclick = function(){
          console.log("点击事件触发了！！");
      };
  </script>
  ```

- onmouseenter——鼠标移入事件

  ```html
  <div id="main"></div>
  <script>
  	var oM = document.getElementById("main");
      // 节点 . 事件 = 执行函数
      oM.onmouseenter = function(){
          console.log("鼠标移入了！！");
      };
  </script>
  ```

- onmouseleave——鼠标移出事件

  ```html
  <div id="main"></div>
  <script>
  	var oM = document.getElementById("main");
      // 节点 . 事件 = 执行函数
      oM.onmouseleave = function(){
          console.log("鼠标移出了！！");
      };
  </script>
  ```

- onmousedown——鼠标按下事件

  ```html
  <div id="main"></div>
  <script>
  	var oM = document.getElementById("main");
      // 节点 . 事件 = 执行函数
      oM.onmousedown = function(){
          console.log("鼠标按下立马触发事件！！");
      };
  </script>
  ```

- onmouseup——鼠标抬起事件

  ```html
  <div id="main"></div>
  <script>
  	var oM = document.getElementById("main");
      // 节点 . 事件 = 执行函数
      oM.onmouseup = function(){
          console.log("鼠标抬起时立马触发事件！！");
      };
  </script>
  ```

- onmousemove——鼠标移动事件
  *只要鼠标在动就会一直触发该事件*

  ```html
  <div id="main"></div>
  <script>
  	var oM = document.getElementById("main");
      // 节点 . 事件 = 执行函数
      oM.onmousemove = function(){
          console.log("鼠标移动就触发事件！！");
      };
  </script>
  ```

- 事件小练习

  ```html
  <div id="main"></div>
  <div id="nav"></div>
  <script>
  	var oM = document.getElementById("main");
      oM.onclick = function(){
  		this.innerText = "点击添加文字";
      };
      // 事件函数
      oM.onclick = function(){
  		this.innerText = "点击添加文字";
      };
      //事件函数的复用（不同的元素节点是同一种事件时使用事件函数复用）
      function goudan(){
          this.innerText ="点击添加文字";
      }
      //千万不能家goudan()加括号
      oM.onclick =goudan;
  	oN.onclick =goudan;
  </script>
  ```

