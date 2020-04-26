# 基础DOM操作

- 获取HTML元素的方式（标签/元素/节点）

  ```js
  //通过ID获取：
  document.getElementById("godan");
  //通过class获取：（不兼容IE8及以下）
  document.getElementsByClassName("warp");
  //通过标签名获取：
  document.getElementsByTagName("div");
  //通过选择器
  document.querySelector("#goudan .warp");//单个获取
  document.querySelectorAll();//多个获取
  
  //通过name属性获取：（极为少用，一般在表单里面使用）
  document.getElementsByName();
  ```

- 获取元素详解

  ```html
  <div id="nav"></div>
  <p class="goudan">123456</p>
  <p class="goudan">123456</p>
  <p class="goudan">123456</p>
  <script>
  	var oNav = document.getElementById("nav");
      //只能获取单个元素节点
  	var x = document.getElementsByClassName("goudan");
      //获取到的是一个集合（不管获取的是一个还是多个，得到都是一个集合）
      console.dir(oNav);
      //打印结果：oNav存储的是一个单个节点对象
      console.log(x);
      //打印结果：x存储的是一个数组结构，这个数组结构里面存放了多个节点。
      oNav.innerText = "刷机大师客单价快点结束";
      //可以直接对节点对象进行点操作。
  	x[0].innerText = "刷机大师客单价快点结束";
      //必须先把数组结构里的节点对象拿出来，再进行点操作。
  </script>
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
  </script>
  ```

- 6.303

