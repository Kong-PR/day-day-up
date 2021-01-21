### CSS学习笔记

- 选择器

  - id选择器：通过#idname实现选择，只能在HTML中出现一次  
    ![image-20210116165503794](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210116165503794.png)

  - 类选择器：通过.classname实现选择，可以在HTML中出现多次  
    ![image-20210116165534803](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210116165534803.png)

  - > 二者名字都不能以数字开头，有的浏览器不支持

  - 标签选择器：通过HTML标签来实现选择  
    ![image-20210116165610285](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210116165610285.png)

  - 内联选择器：直接写在标签内部  
    ![image-20210116165347490](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210116165347490.png)

  - > 这四种 CS 选择器有修饰上的优先级，即：
    >
    > 内联选择器 > id选择器 > 类选择器 > 标签选择器

- CSS创建
  - 样式表分为三种：外部样式表、内部样式表、内敛样式表
  - 多重样式表的层叠优先级：  
    ![image-20210116170856434](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210116170856434.png)  
    ![image-20210116170938596](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210116170938596.png)  
  - ![image-20210116171210218](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210116171210218.png)  

- 盒子模型
  
  - ![image-20210116193116647](https://raw.githubusercontent.com/Kong-PR/Typora-picture/master/img/image-20210116193116647.png)
  
- css元素类型

  - 块元素：独占一行，文字元素里不能放div
  - 行元素：一行可放置多个元素，不能设置宽和高，一般不能放块内元素
  - 行内块元素（查不到）：有二者的部分特点，可以设置宽和高 例如表单
  - 模式转换：display:block  inline  inline-block
  - 

