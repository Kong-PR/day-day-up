# VUE学习笔记

## 基础

### Vue初体验

- 基本特点
    - let 常量、conset变量
    - ES6中尽量不使用var
    - 响应式一边改一边变-
    
- Vue生命周期
    - 类似对象的生命周期，构建函数、析构函数
    ![20210122084824](https://cdn.jsdelivr.net/gh/Kong-PR/Typora-picture@master/img/20210122084824.png)
    红色为钩子函数，可以用户自己添加，绿色是框架本身实现的
    - beforeCreate created mounted
    - 有回调

### 插值操作

- 插值操作

  - Mustache（胡子）: {{message}}
    - 可以写简单的表达式：{{lastname+firstname}}
  - v-once：防止同时变化（相当于第一次展示数据，后面不变化）
  - v-html：自动解析HTML语句 v-html=""
  - v-text：效果同mustache，但不够灵活。v-text="message"
  - v-pre：相当于不解析 {{}}，原封不动的显示出来
  - v-cloak：vue解析前div中有cloak，解析后无，style中display:none，一般不用

### 动态绑定属性

- 动态绑定属性

  - 基本使用

    - v-bind:src="message"，动态绑定图片
    - 语法糖 直接写个冒号:

  - 动态绑定class

    - <h2> :class:"{active:true,line: false}"></h2>h2>

    - 对象语法，数组语法

  - 动态绑定style

    - 对象、数组

### 计算属性

- 计算属性

    - computed：funname:gunction(){}
    - 有缓存，多次调用，只计算一次，性能较高 不需要加()调用
    -  set、get 一般没有set方法，相当于只读属性
        ![image-20210123132440478](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210123132440478.png)

### 事件监听

- 事件监听

    - v-on： click、keyup、
      - 需要参数：需要括号；如果需要参数但是没有传入，函数形参为undefined；如果没有括号，传入浏览器生成的event对象；获取浏览器产生的参数，可以用$event
        ![image-20210123193813804](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210123193813804.png)
      - 不需要参数：不需要括号
      - 简写为 @
      - 修饰符：stop 阻止冒泡；  prevent 阻止默认事件 keyup 键盘监听 once 只一次
        ![image-20210123200044608](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210123200044608.png)

### 条件判断

- 条件判断

    - v-if else elseif（不推荐的）、v-show
      - 用于切换元素的显示状态
      - if会完成删除该元素
      - show仅调整元素的display属性，功耗小
        ![image-20210123202836864](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210123202836864.png)
    - v-bind
      - 为元素绑定属性
      - v-bind:属性
      - 简写为:

### 循环遍历

- 循环遍历

    - v-for
      - 遍历数组、对象  
      - ![image-20210118091326276](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210118091326276.png)
      - ![image-20210124150742632](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210124150742632.png)
      - 遍历元素时，数组渲染之后，插入元素渲染过程 
        ![image-20210124152559589](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210124152559589.png)
      - 哪些数组的方法是响应式的
        - push、pop、shift、unshift、splice、sort、reverse
        - 通过索引修改数组中元素，不是响应式

### model的使用

- v-model

    - 双向数据绑定，设置表单元素的值  
    - ![image-20210118094430932](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210118094430932.png)
    - 联动radio
      - ![image-20210124191727260](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210124191727260.png)
    - 联动checkbox
      - ![image-20210124192635494](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210124192635494.png)
    - 联动 select
      - ![image-20210124193518571](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210124193518571.png)
    - 值绑定
      - ![image-20210124194057873](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210124194057873.png)
    - 修饰符
      - lazy 在失去焦点或回车的时候在更新
      - number 指定绑定类型为number，就不需要类型转换了
      - trim 去除空格
      - ![image-20210124194932294](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210124194932294.png)

## 进阶

### 组件化开发

#### 基本使用

- 组件化
  - 思想：开发出一个个可服用的小组件来构造我们的应用，任何的应用都会呗抽象成一刻组件树，使代码方便组织和管理，易拓展
  - 组件使用：创建组件构造器、注册组件、使用组件
- 基本使用
  -  ![image-20210124221918119](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210124221918119.png)
  - 现在使用更多的语法糖，有些不会经常看到这种基础方式了
- 全局组件和局部组件
  - 全局组件可以在多个vue的上实例下使用
  - 局部组件，在vue创建声明里使用

#### 父子组件

-  父组件和子组件
  - ![image-20210124225407757](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210124225407757.png)
    ![image-20210124225453581](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210124225453581.png)
  - ![image-20210124230207662](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210124230207662.png)
- 语法糖注册方式
  - vue.extend -> 直接到注册那一步
    ![image-20210124230423328](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210124230423328.png)
    ![image-20210124230532556](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210124230532556.png)
- 模板分离
  - script标签、template标签
    ![ ](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210124231228586.png)
- 组件内部有data数据，必须是函数，返回对象，保存对应属性。
  ![image-20210127193440611](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210127193440611.png)
  - 为什么呢？保证数据独立，多次调用数据不互相影响
    ![image-20210127194542371](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210127194542371.png)
    
  - props用法 父组件传递数据到子组件，*需要多记，多练*
    
    - ![image-20210130152546249](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210130152546249.png)
      ![image-20210130152603807](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210130152603807.png)
    - 多种写法
      ![image-20210130154119043](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210130154119043.png)
    - 驼峰的使用
      ![image-20210130155019426](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210130155019426.png)
    
  - 子组件传递数据给父组件
  
    - ![image-20210130162206582](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210130162206582.png)
  
      ![image-20210130162349516](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210130162349516.png)
      ![image-20210130162404672](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210130162404672.png)
  
  - 父子组件实现双向绑定，需要使用发射事件和绑定事件
    ![image-20210130203038651](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210130203038651.png)
  
  - ![image-20210130204701007](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210130204701007.png)
  
  - watch作用
  
    - 监听属性的变化，对应做出改变
      ![image-20210130205142527](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210130205142527.png)
  
  - 父访问子 两种 children refs **其中refs使用较多**
    ![image-20210130211127540](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210130211127540.png)
  
  - 子访问父 parent
    ![image-20210130211740196](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210130211740196.png)
  
  - 访问根组件 root

#### 插槽

- 目的
  - 让封装的组件具有可拓展性
  - 让使用使用这事儿决定最终展示什么
- 如何
  - 保留共性，去除不同
- 基本使用
  - ![image-20210130214510992](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210130214510992.png)
- 具名插槽
  - ![image-20210130214946728](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210130214946728.png)
- 编译作用域
  - 使用当前模板下的变量，相当于把cpn当做是一个div
    ![image-20210131104344821](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210131104344821.png)
  - ![image-20210131104606439](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210131104606439.png)
  - 作用域插槽 父组件替换子组件的展示，使用子组件的内容
    ![image-20210131105826300](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210131105826300.png)

### 模块化开发

- 公共变量命名重复的问题

  - ES5：匿名函数实现模块化
    ![image-20210131185809988](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210131185809988.png)
  - 常见的模块化规范：commandJS、AMD、CMD还有ES6的Modules
  - commomjs的导入导出
    ![image-20210131190643776](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210131190643776.png)

- ES6的模块化

  - 导出
    ![image-20210131192219391](../../../AppData/Roaming/Typora/typora-user-images/image-20210131192219391.png)
    ![image-20210131200516150](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210131200516150.png)

  - 导入

    ![image-20210131200916304](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210131200916304.png)

    ![image-20210131201014884](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210131201014884.png)

## webpack

![image-20210131203110629](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210131203110629.png)

### webpack的使用

#### 起步

- 77













































> 虚拟dom的复用问题，使用key标记![image-20210123211349561](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210123211349561.png)
>









## ES6语法

- var 可以当做js语言设计上的错误，为了修复这个问题，有了关键字let 用来替换var
- 块级作用域：var 没有块级作用域
- js 中，只有函数有作用域，if for都没有作用域，所以很多时候需要借助function的作用域来解决这个问题，ES6中加入let，有块级作用域
- const 常量，优先使用const，对象不能修改，但是可以改变对象内部的属性
- 对象的增强写法
  ![image-20210123165714044](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210123165714044.png)
- 函数的增强写法
  

## 高阶函数的使用

- 编程范式
  - 命令式编程、声明式编程
  - 面向对象编程（第一公民：对象）、函数式编程（第一公民：函数）
  - 高阶函数 filter map reduce（函数需要的参数也是函数）
    - ![image-20210124170945876](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210124170945876.png)
    - ![image-20210124183936803](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210124183936803.png)
    - ![image-20210124184548818](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210124184548818.png)
  - 