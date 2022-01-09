### 1. 概念

- [ ] MVVM（Model-View-ViewModel）模式是一种简化的用户界面的**事件驱动编程方式**，源自于MVC（Model-View-Controller）模式。	**其核心是ViewModel层，负责转换Model中的数据对象让数据变得更容易管理和使用。**
  - 向上与视图层进行双向数据绑定  
  - 向下与Model层通过接口请求进行数据交互

  ViewModel访问Model数据通过Ajax，Model向ViewModel传输数据使用Json串。

  - Vue中引入ViewModel的优势：**完全解耦了View层和Model层**

  Vue的核心就是实现了DOM监听和数据绑定

  理解DOM监听和数据绑定：

  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <title>vue_first</title>
  </head>
  <body>
  
      <!--View层,模板-->
      <div id="app">
          {{message}}
      </div>
  
      <!--1.通过cdn方式，导入vue-->
      <script src="https://cdn.jsdelivr.net/npm/vue@2.6.12/dist/vue.min.js"></script>
      <script>
          var vm = new Vue({
             // 绑定元素
             el: "#app",
              //Model层,数据
              data:{
                 message:"hello vue"
              }
          });
      </script>
  </body>
  </html>
  ```

  当在浏览器中的console中变换vm.message的值时，页面显示会相应的发生变化而无需刷新，即以上所说的ViewModel层，**包含数据的状态和行为，使用观察者模式来实现数据的监听与绑定，以做到数据与视图的快速切换**。