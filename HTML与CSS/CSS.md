页面重构师：将psd设计稿用html、css技术转化为静态页面

## 1、CSS规则：
       CSS规则 = 选择器 + 声明块



   ### 选择器样式添加理解：
               中间没有空格：       同时满足
               中间有空格、大于号： 为该元素的子元素
               中间有冒号：         为该状态（后）下的元素（前）
               中间两个冒号：       为该元素生成一个元素，加样式
               中间有加号：         为该元素的下一个元素
               中间有减号：         为该元素的上一个元素



   ### 选择器：选中元素（确定样式的应用范围）,应用给谁
               （帮助你精准的选中想要的元素）

              写法：1、元素选择器
                             格式：
                                 直接在style里书写---元素名字 + 花括号
                               --写上元素的名称，应用给该元素
                                可以选中给页面的所有同名元素

<head>
     <style>
        h1
        {
         color:red;
         background-color=blue;
        }
     </style>
</head>

                    2、id选择器
                             格式：
                                先为应用元素设置id
                                再在style里书写---# + id名字 + 花括号
                            --选中的是对应id值的元素

<head>
     <style>
        #text
        {
         color:red;
         background-color=blue;
        }
     </style>
</head>

<body>
      <p id="test">asdasd</p>
</body>

                    3、类选择器
                             格式：
                                先为应用元素设置class
                                再在style里书写--- . + class名字 + 花括号
                            --一个元素的class可以使用多个，中间可用空格隔开
                              即：一个元素可使用多个样式

<head>
     <style>
        .text
        {
         color:red;
         background-color=blue;
        }
     </style>
</head>

<body>
      <p class="test">asdasd</p>
</body>

        
        
        
   ### 声明块：出现在大括号中，包含多个声明（属性）
                每一个声明表示每一个样式规则



## 2、CSS代码书写位置



   1. 内部样式表：
                  书写在style里，并把该元素放在head里（为了浏览器加载时先加载css代码）
                  格式：正常的CSS选择器写法

<head>
   <style>
     hr {color:sienna;}
     p {margin-left:20px;}
     body {background-image:url("images/back40.gif");}
   </style>
</head>

   2. 内联样式表（元素样式表）：
                  书写在style里，并把该元素放在应用元素标签里（不需要再写选择器）直接应用
                  格式：style=“。。。。”（放置在元素标签内）

<p style="color:sienna;margin-left:20px">这是一个段落。</p>

   3. 外部样式表:
                  将样式书写到独立的CSS文件中
                  格式：
                   
                        CSS代码里：     
                                 直接在css文件里书写css规则，其他什么都不用添加
                        
                        
                        html代码里
                                 1.要先在head里写一个新的元素link，在href里写上引用的css文件按的链接
                                （别人网站的css用绝对路径,带http的；自己网站的css用相对路径 类似css/css.css）

<head>
<link rel="stylesheet（css类型）" type="text/css" href="mystyle.css（本地css代码链接）">
</head>

                                 2.再在应用元素的标签里写上对应的class
        
         
          外部样式表：避免多个页面使用同一样式，重复写样式代码
                    有利于浏览器缓存，从而提高页面响应速度（直接用以前读到的放在缓存里的css代码）
                    有利于代码分离，更容易阅读和维护 




## 3、常见样式声明



   1. color  元素内部的文字颜色

        格式：color 冒号 属性值

        属性值：1.预设值：使用定义好的颜色单词
                2.三原色，色值：
                              2.1：  rgb表示法，三个10进制数字代表红绿蓝：
                                                color:rgb（0，0，0）                       
                              2.2：  hex表示法，三个16进制数字代表红绿蓝：
                                                color：#00ff00


   2. background-color   元素背景颜色

        格式：color 冒号 属性值

        属性值：1.预设值：使用定义好的颜色单词
        
                2.三原色，色值：
                              2.1：  rgb表示法，三个10进制数字代表红绿蓝：
                                                color:rgb（0，0，0）                       
                              2.2：  hex表示法，三个16进制数字代表红绿蓝：
                                                color：#00ff00

                                                
   3. font-size   元素内部文字的尺寸大小

        格式：fount-size 冒号 数值 

        单位：1.px（像素）：文字的高度占多少个元素，像素越大文字越大
              2.em:         相对于父元素大小的倍数（最终会换算为像素单位）
             每个元素必须要有字体大小，如果没有声明，使用父元素字体大小
             如果没有父元素，使用基准的默认字体大小（基准16px）


   4. font-weight     文字粗细陈程度（可以取值数字，也可以取预设值）

        格式：fount-weight 冒号 数值 值

        值：  1.数值：有些数值可能并不管用：因为字体在设置时可能没有适配一些粗细
              2.预设值： 1.normal（默认==400）
                         2.bold（加粗==700）
              3.strong元素默认加粗
                 strong：表示重要的内容；



   5. font-family     文字字体类型

        格式：fount-family 冒号 字体类型1，文字类型2

        字体类型： 浏览网页的人有这个字体才能看见
                   原则：使用多个字体，以匹配不同环境
                   sans-serif该类型为非衬线字体：防止用户什么字体都没有（中文）
                   默认类型：consolas、翩翩体-简，微软雅黑，Arial,sans-serif


   6. font-style     字体样式-斜体

        格式：fount-style 冒号 字体类型1，文字类型2
        
        特殊：i元素、em元素默认为斜体，i常用于表示图标（icon）；em表示需要强调的内容
              斜体：italic；正常：normal


   7. text-decoration     文本修饰，给文本加线
        格式：fount-decoration 冒号 加线类型
        加线类型： line-through:从文本中间穿过
                   overline:文本上方加线
                   underline:下划线
                   none：没有线（可用于超链接去掉下划线）

            默认使用line-through的元素:del元素：错误的元素；s元素：废弃不再使用的元素    


   8. line-indent      首行文本缩进
         格式：line-index 冒号 数值与单位
         数值单位： 1.px、em
    
    
   9. line-height    行间距；每行文本的高度；值越大每行文本距离越大
         格式：line-height 冒号 数值单与位
         设置行间距为容器的行间距，可以让单行文本垂直居中（上下居中）
         行间距，可设置为纯数字，表示行间距为当前字体大小的高度
    
    
   10. width     宽度

         格式：width 冒号 数值与单位


   11. height    高度

         格式：height 冒号 数值与单位


   12. letter-space     字间距

         格式：letter-space 冒号 数值与单位


   13. text-align      元素内部文字的水平排列方式
         格式：text-align 冒号 排列方式类型
         排列方式类型：left、center、right






## 4、特殊选择器

   1. 通配符选择器  *

        格式：css代码里

       <!-- 选中所有元素使他们发生改变 -->

           *{
            color:red;
           }

        作用：html所有代码元素全部应用该样式



    2. 属性选择器    []
              根据属性名、属性值选中元素
        
        格式：css代码里

           <!-- 选中所有具有href属性的元素 -->

            [href]{
                color:red;
            }

           <!--  选中所有具有href属性,且属性值为的元素-->

            [href=“asdas.com”]{
                color:red;
            }

            ([href$="以。。结束的链接“]{。。})

        作用：html所有具有该属性，或属性值为设定的元素应用该样式
        （不止这些用法，可以搜索手册查看）
    


    3. 伪类选择器   :
              选中某些元素的某种状态

              需要搭配元素一起使用（四大主要伪类，全部应用时须按顺序书写添加：爱恨法则：lvha，love hate）
                  hover：鼠标悬停状态
                  active：激活状态，鼠标按下状态
                  link：超链接未访问时的状态
                  visited：超链接访问过后的状态

        格式： css代码里
            <!-- 鼠标悬停状态-----在此时令某些元素发生改变 -->

             :hover{
                  color:red；
             }

           <!-- 鼠标悬停状态----在此时令a元素发生改变 -->

             a:hover{
                  color:red;
             }

           <!-- 鼠标按下（激活）状态----在此时令a元素发生改变 -->

             a:active{
                  color:blue;
             }



      4. 伪元素选择器     : :
                 生成并选中某个元素内部的第一个子元素或最后一个子元素

        格式：css代码里
            <!-- 在span元素里创建子元素，并在span元素前面显示《这个东西 -->
              span::before{
                  content:《;  //创建《
                  color:red;  //只有子元素应用这个样式
              }


           <!-- 在span元素里创建子元素，并在span元素后面显示《这个东西 -->
              span::after{
                  content:《;  //创建《
                  color:red;  //只有子元素应用这个样式
              }


              html代码里
                    <p>阿斯顿<span>啊啊啊</span>阿斯顿撒</p>






## 5、 选择器的组合

   1. 元素的并且组合：必须所有条件（class、元素id等等）都满足才会应用到元素上
           格式：两个选择器（中间不加空格）
      eg：
         <!-- 只有    同时满足     为p元素，且类别为abc     才能应用该样式 -->

      css里：

         p.abc{
            color:red;
         }

      html里：

         <p class="abc">啊啊啊</p>



   2. 后代元素（子元素）应用样式：--------空格
          格式： 两个元素，中间加空格（元素可写多个进行嵌套）
                 元素1 空格 后代元素（子元素）花括号
        eg：
          <!-- 对     元素内部的  列表          加样式 -->

          css里：
             .red li{
                  color:green;
             }

          html里：
             <div class="red">
                <ul>
                  <li>123</li>               
                </ul>        
             </div>   


    3. 子元素选择器组合----->
           同上：将空格变为大于号">"-----但是只能选中下面的一个子元素，限制比上面小
           并且，只能是邻近的下一个子元素


    4. 相邻兄弟元素--------+
           格式：选中元素  +  下一个元素的id或者元素名等等  {}
            eg：
          <!-- 对元素内部的列表的选中行的下一行加样式 -->

          css里：
             .red special+li{
                  color:green;
             }

          html里：
             <div class="red">
                <ul>
                  <li class="special">123</li>  
                  <li>2233</li>             
                </ul>        
             </div>   


    5. 后面出现的所有兄弟元素--------~
            格式：选中元素  ~  下一个元素的id或者元素名等等  {}

            同上



## 6、选择器的并列

多个选择器，用逗号分隔
        将两个需要使用相同样式的元素，结合到一起
        （与组合不同，组合需要同时满足两个条件，并列，只要是写到的元素都会应用该样式）     
        （可写多个选择器）
            
             .red li，a:hover{
                  color:green;
             }


## 7、层叠（权重计算）

   1. 声明冲突：同一个元素可能被多个样式影响，其中不同样式可能有相同的属性值，会对元素造成影响（比如一个改红色，一个改蓝色）

   声明冲突总是会有的，是不可避免的，也是需要认为制作的
   比如列表全部用红色，其中某一个我们单独设置颜色

   2. 层叠：解决声明冲突的过程，浏览器自动处理
       步骤：
         1.比较重要性

               重要性从高到低排序为：

                  1、作者样式表（开发者样式表）中的！important样式

                     -----在某一个样式规则后面加！important
                          eg：
                             a{
                              color:red !important;
                             }
                          (不建议用，因为级别太高，其他样式无法覆盖)

                  2、作者样式表的普通样式

                  3、浏览器默认样式表



         2.比较特殊性

             解决    重要性方法 没法解决    的时候

             总体规则：看选择器（选择器选中的范围越小越特殊）

             具体规则：通过选择器，计算出4位数：数值越大越特殊
                                                            (逢256进1)
                    步骤：
                         1、千位：如果为内联样式，记1，否则记0
                                             eg：
                                                <a class="red" style="color:blue>啊啊啊</a>
                                                蓝色大于红色，内联大于内部，千位记1

                         2、百位：等于选择器中所有id选择器的数量
                                             eg：
                                               css代码：
                                                  a{        
                                                   color:red;    //元素选择器
                                                  }
                                                  #my{
                                                   color:blue;   //id选择器
                                                  }
                                                  .sec{
                                                   color:green;  //类选择器
                                                  }
                                                html代码:
                                                 <a id="my" class="sec">啊啊啊</a>

                                          为蓝色，因为不是内联，千位为0，百位，id为1，优先id选择器

                         3、十位：等于所有选择器中所有  类选择器、伪类选择器、属性选择器  数量之和
                         4、个位：等于所有选择器中所有  元素选择器、伪元素选择器  数量之和



                         eg：
                         -----------------------------------------------------
                            <style>
                                 a{
                                    color:red;   //a
                                 }
                                 div ul a{
                                    coloe:pink;   //div的ul的a
                                 }
                                 #my #he :link{
                                    color:blue;   //my的 he的 link
                                 }
                                 #my #he a:link{  //my的 he的 选中link状态时的 a
                                    color:green;
                                 }
                            </style>

                            <div>
                              <ul id="my">
                                <li id="he">
                                  <a class="link">啊啊啊</a>
                                </li>
                              </ul>
                            </div>
                       ------------------------为绿色-------------------------
                                           
         3.比较源次序

                 代码书写靠后的胜出
                 
                 1、对于书写的css文件：我们通常用link在html代码中引用
                                 1.1、link引用的文件中，靠下一行的（靠后）的  覆盖   上一行的
                                 2.2、作者样式表大于浏览器样式表

                 2、对于在同一个css样式规则里的属性值，若一样，靠后的覆盖前一个

   3. 应用
          1.重置样式表
              书写作者样式表，覆盖浏览器默认样式

              常见的重置样式表：normalize.css;reset.css;meyer.css

          2.爱恨法则（link；visited；hover；active）
               依据源次序，靠后的胜出，点击被激活后会一直是active的状态

               eg：
                  a:link{
                     color:red;
                  }
                  a:visited{
                     color:green;
                  }
                  a:hover{
                     color:blue;
                  }
                  a:active{
                     color:pink;
                  }



## 8、继承 

   1. 子元素会继承父元素的某些css属性
          继承是递归的：子元素的子元素也会继承父元素的css属性

   2. 通常与文字相关的属性是会被继承的


## 9、属性值的计算过程（页面渲染过程）


   1. 浏览器的渲染原理

    一个元素一个元素依次进行渲染；
    其顺序 按照页面文档的树形目录结构 进行一个一个节点元素 的渲染；

             其中：
                 渲染每个元素的前提条件：该元素的所有的css属性必须有值

                 （平常书写代码时，只要写自己想要的css属性即可，但实际渲染时，一个元素必须所有css属性全部确定下来，浏览器才会渲染这个元素）

   2. 属性值计算过程：（对于html的元素来说）

            一个元素，从所有属性都没有值，到所有属性都有值，这个计算过程叫做  属性值计算过程

         步骤：

             对于html的某一个元素，先找到加载在对象身上的所有的css样式表
             
             1、确定声明值 
                  
                  通过对比规则，找到参考样式表中 没有冲突 的属性值，直接作为该元素的确定css属性

   <!-- 声明针对的是某一个元素，而非样式表有没有相关的，就算有相关的，之哟啊不是确切的，都划归为声明之后，属于继承的范畴 -->
             
             2、层叠冲突解决
                  
                  通过层叠规则，找到参考样式表中 唯一覆盖 的属性值，然后作为该元素的确定css属性

             3、使用继承
                 
                  通过继承规则，对于  仍然没有值  的属性，若可以继承，则继承父元素属性值，然后作为该元素的确定css属性

             4、使用默认值
               
                   对于仍然没有值的属性，使用默认值


### 经典问题：a元素为什么没有继承
      div{
         color:red;
      }

      <body>
          <div>
            <a href="">啊啊啊</a>
            <p>钱钱钱</p>
                              
          </div>
      </body>
### 结论：钱钱钱是红颜色；啊啊啊是紫色
### 因为先声明值，在层叠，在继承，a元素在浏览器中已经有了默认的声明值，且没有冲突，所以直接默认就不继承了 


###    特殊的两个css值-----令某个元素属样式性值等于这俩

  1. inherit：手动（强制）继承，将父元素的值取出应用到该元素上

  2. initial：初始值，将该元素的属性值设为默认值
  





## 10. 盒模型
            规定单个盒子的规则

   
   1. box盒子：每个元素  都会生成一个矩形区域（盒子）  在页面中显示出来
        
        盒子：css概念；元素：html概念

   2. 盒子类型:（css的一个样式规则，display）

       1. 行盒：display等于inline的元素，在页面中不换行，页面中的一行里的一小段（为浏览器默认值）
       2. 块盒：display等于block的元素，在页面中独占一行，页面中的一大行

       * 内容盒（content-box）：内容区
       * 填充盒（padding-box）：填充区+内容区
       * 边框盒（border-box） ：边框区+填充区+内容区


       常见的块盒：容器元素、h1-h6、p
       常见的的行盒：span、a、img、video、audio
       （可互相转化）

   3. 盒子的组成部分

            无论是行盒还是块盒，都有下面几个部分组成
            从内到外：

                1. 内容 content

                    内容部分通常叫做整个盒子的的内容盒 content-box
                   
                   属性值：
                       1.width、height：设置的是盒子内容的宽高 


                2. 填充（内边距） padding 

                      盒子边框到盒子内容的距离

                      属性值：
                          1.padding-left、padding-right、padding-top、padding-bottom
                          2.padding速写属性：padding：上 右 下 左
                                             padding：上下（一个值）   左右（一个值）
                                             padding：一个值（四周同一值）


                3. 边框 border

                     边框 = 边框样式（border-style） + 边框宽度（border—width/height/...） + 边框颜色（border-color）

                     边框样式：默认为none；     
                     边框颜色：默认为字体颜色；
                     边框宽度：可简写：border-width:上 右 下 左

                     速写属性： border：宽高、样式、颜色


                4. 外边距 marign

                     边框到其他盒子的距离

                        属性值：
                          1.margin-left、margin-right、margin-top、margin-bottom
                          2.margin速写属性： margin：上 右 下 左
                                             margin：上下（一个值）   左右（一个值）
                                             margin：一个值（四周同一值）



## 11. 盒模型的应用


   ### 1. 改变宽高范围

               默认情况下，width与height设置的是内容盒的宽高

               所以当拿到设计师的设计稿时，  某个列表的宽高，实际尺寸   指的是--->边框盒的宽高

               但是使用width和height改变的是内容盒的宽高，后需更改尺寸时会有问题。

               解决办法：

                   设置box-sizing属性：改变宽高的影响范围

                       1. box-sizing：content-box          //宽高影响内容盒
                       2. box-sizing：border-box           //宽高影响边框盒



   ### 2. 改变背景的覆盖范围

                  默认情况下，背景  覆盖   边框盒的背景（边框到内容的全部范围的背景颜色全被设置）

                  解决办法

                      设置background-clip属性：改变背景颜色覆盖范围

                          1.content-box   //只覆盖内容盒
                          2.border-box    //只覆盖边框盒
                          3.padding-box   //只覆盖填充盒


   ### 3. 溢出处理  （内容超出边框的错误解决，对于溢出字符的处理）

                不设置高度时，盒子的宽高会随着内容的增加而增加；
                设置高度时，内容可能会超出盒子的设定范围

                解决办法：
                      设置overflow属性：控制内容溢出边框盒的处理方式

                         1.overflow:hidden    //溢出部分隐藏
                         2.overflow:visible   //溢出部分可见
                         3.overflow:scroll    //边框滚动条
                                  overflow-x:scroll //只显示横向
                                  overflow-y:scroll //只显示纵向
                         4.overflow:auto      //需要滚动条出现，不需要不出现，依据边框盒的宽高来看
                         
                         * 5.text-overflow：ellipsis  //对于单行文本溢出的内容使用原点代替！！！！！！！！


   ### 4. 断词规则  （在什么位置换行）

             会影响文字在什么位置被截断换行

             解决办法：
                   设置word-break属性：进行截断自设置

                             1. normal：普通：         对于cjk字符（文字位置截断）；
                                                           非cjk字符（单词位置截断）

                             2. break-all：截断所有：  对于所有字符，在所有位置截断；

                             3. keep-all： 保留所有：  对于所有字符，在字符与字符间截断；


   ### 5. 空白处理   （对于显示的内容进行不换行的处理）


              解决办法：
                   设置white-space属性：进行空白字符的处理

                        1. white-space:nowrap     //不换行





   #####  对于单行文本的溢出处理----使溢出的内容用原点代替
        对于样式进行如下处理
          li{
            white-space：nowrap;
            overflow:hidden;
            text-overflow:ellipsis;
          }




## 12. 行盒的盒模型


   1. 显著特点：
            1. 盒子沿着内容延申
            2. 行盒间头尾相接
            3. 行盒不能设置宽高-----调整行盒宽高，要通过  字体的大小宽高等参数  间接调整

            4. 填充区padding： 水平方向有效；垂直方向只会影响背景，但不影响文字空间
            5. 边框区borde：   水平方向有效；垂直方向只会影响背景，但不影响文字空间
            6. 外边距margin：  水平方向有效；垂直方向只会影响背景，但不影响文字空间
   

   2. 常见的行盒
         包含具体内容的元素：span、strong、img、view、audio、em、i、a



## 13. 行块盒

          display：inline-block的盒子

   1. 特点：
        1. 不独占一行
        2. 盒模型中所有尺寸都有效

        可以和行盒一样，水平排列在一起，但是又可以设置宽高

   2. 应用：做页面导航栏的分页数字按钮
   

.page a{
   border：1px solid #e1e2e3;  //设置边框颜色
   text-decoration：none；     //去掉底部下划线
   color：#38f；               //设置字体颜色
   display：inline-block；
   width：34px；
   height：34px；              //设置行块盒，以改变元素宽高
   text-align：center          //内部文字居中排列
   line-height：34px           //单行文本垂直居中    
  }
<div>
<a href=" ">1</a>
<a href=" ">2</a>
<a href=" ">3</a>
<a href=" ">4</a>
<a href=" ">5</a>
<a href=" ">6</a>
<a href=" ">7</a>
</div>


   ###  空白折叠

     空白折叠发生在，行盒（行块盒）内部、 行盒（行块盒）之间

   ###  可替换元素  与  非可替换元素
   
      大部分元素：页面上显示的结果，取决于元素内部的内容
      少部分元素：页面上显示的结果，不取决于元素内部的内容-----称为：可替换元素

      可替换元素：（显示内容取决于某些属性）----  均为： 行盒
                   img、video、audio

                   但：  虽然是行盒，类似于行块盒，但是可以设置宽高，所有尺寸均可设置

        eg：
            对于img元素：
               1. width与height：改变整个盒子，里面的图片内容也会相应拉伸
               2. object-fit：图片适应方式
                         contain：保持原比例且图片不溢出
                         fill：   显示全部内容，填充在盒子内
                         cover：  把区域填充满，且不改变比例，但损失信息
                         默认fill




## 14. 视觉格式化模型（布局规则）

          页面中的多个盒子的排列方式

          大体上将页面中的盒子的排列分为三种方式
               1.常规流
               2.浮动
               3.定位
          
   ### 1. 常规流（文档流）------   所有元素默认情况下，都属于常规流布局

         1. 常规流布局（文档流、普通文档流、常规文档流）
               

         2. 总体规则：块盒独占一行、行盒水平依次排列

         3. 包含块（containing block）：包含块决定了每个盒子的活动范围
                                        每个盒子都有它的包含块

         4. 绝大多数情况下：盒子的包含块，为其父元素的内容盒



         <!---------------- 对于块盒 的 常规流样式（宽度） 介绍 ----------------------->

         1. 每个块盒的宽度正好等于包含块的宽度； 


         2.  宽度的默认值为auto：表示将剩余空间吸收掉
             margin的默认值为0，但也可取值为auto，表示吸收能力

             但是：width吸收能力强于margin，他俩发生冲突时，空间先分配给width

        
         3.  若宽度、边框、内边距数值完全确定，但仍有剩余空间，该空间由margin-right占据
             若在设置上margin-left、margin-right均等于auto，块盒在其包含块内居中
                -----即：在常规流中，块盒在其包含块内居中，可以定宽，然后左右margin设置为auto


         4.  每个块盒的垂直高度
                            若height设为默认值-auto，则高度由内容决定
                              margin设为默认值-auto，则值为0

         <!------------------------------------------------------------------------ -->

         1. 百分比取值
             
            1. 宽高、padding、margin可以取值为百分比

                其中百分比，相对于的是包含块的宽度！！！！！！
                   即便是高度设置为百分比，相对于的也是包含块的宽度，而非高度


            2. 高度的百分比：
                 1. 当 包含块的高度 取决于子元素的高度（父元素未设置高度，则内容多高，包含块多高）
                                  ---->此时设置百分比无效，高度为auto
                 2. 当 包含块的高度 不取决于子元素的高度（父元素高度已经设定好了）
                                 ----->此时百分比是相对与父元素的高度


            <!--   -------------------------------------------------------------    -->


         1. 上下外边距

                  1. 两个常规流 块盒，上下外边距相邻，会进行合并，
                     margin进行了重叠（上块盒的margin-bottom与下块盒的margin-top重合）
                     
                  2. 两个外边距重合部分的数值取两者最大值

                  3. 父子元素之间外边距也会重叠
                      -----若对父元素设置一些元素（只要将父子元素隔一些东西就可以），则不会重叠
                             eg：设置border或者padding等等
                    
   ### 2. 浮动  float属性

      1. 应用场景：文字环绕、横向排列
      
      2. 浮动的设置：
           
           修改float属性值为：
              - left：左浮动，元素靠上靠左
              - right：右浮动，元素靠上靠右

           默认值为none（不浮动）
      
      3. 浮动的基本特征：

           1. 当一个元素浮动后，元素必定为块盒（强制改变盒子类型）
           2. 浮动元素的包含块，与常规流一样，为父元素的内容盒

      4. 浮动样式下盒子的尺寸：
           1. 宽度为auto时，适应内容宽度
           2. 高度为auto时，与常规流一样，适应内容高度
           3. margin四个方向为auto时，值为0
           4. 边框、内边距、百分比设置与常规流一样

      5. 浮动样式下盒子的排列
           1.  左浮动的盒子靠上靠左排列
           2.  右浮动的盒子靠上靠右排列

           3.  浮动盒子在包含块中排列时，会避开常规流盒子

           4.  常规流块盒在排列时，浮动盒子与常规流盒子无视双方排列

           5.  行盒在排列时，会避开浮动盒子
               （其中对于文字元素，它没有在行盒当中，浏览器会自动生成一个行盒包裹文字）
               （且该行盒叫匿名行盒）


   ### 6.  高度坍塌

         1. 现象：
               子元素脱离父元素
         2. 高度坍塌的根源：
                常规流的高度设置为自动时，在其计算内容的高度时，不会考虑浮动盒子

         3. 解决办法：
              清除浮动：
                涉及css属性的clear ）
                  - 默认值：none  //不清除
                  - left          //清除左浮动，该元素必须出现在前面所有左浮动盒子的下方
                  - right         //清除右浮动，该元素必须出现在前面所有左浮动盒子的下方
                  - both         //清除左右浮动，该元素必须出现在前面所有左浮动盒子的下方
            
            方式1：在所有浮动盒子后面+一个常规流块盒
                   为该盒子设置clear：both
                   ---->便使父元素在底层覆盖了浮动盒子
                     （原理是：新元素排列在所有浮动盒子之后，由新元素撑开了父元素高度）

            方式2：为父元素设置样式---伪元素选择器
                     .clearfix::after{
                        content:"";         //设置内容为空
                        display:block;      //设置元素样式为块盒
                        clear:both;         //设置浮动样式清除
                     }
                     ------>原理同上，只不过是采用伪元素选择器的方式，省略了在html代码中添加一个新元素的步骤，直接在css代码中添加一个样式即可



   ### 3. 定位    position属性

      1. 定义： 手动控制元素在包含块中的精准位置

      2.  设置position属性
           
           - 默认值：   static，静态定位（不定位）
           - relative： 相对定位
           - absolute： 绝对定位
           - fixed：    固定定位

         ！！相对定位为绝对定位提供包含块，固定定位用来打小广告

 <!--    一个元素，只要position的取值不是static，则认为该元素是一个定位元素    -->

      3. 定位元素：会脱离文档（常规）流   （相对定位除外）


      4. 一个脱离了文档流的元素：
          1. 文档流的元素摆放时，会忽略脱离了文档流的元素（类似于常规流与浮动元素相互无视）
          2. 文档流中元素计算自动高度时，会忽略脱离了文档流的元素

   ### 1. 相对定位

         1. 不会导致元素脱离文档流，只是让元素在原来位置上进行一定的偏移
             ---->设置相对定位后，便可以对元素进行位置上的移动

            设置css的属性：
                - left      //离左边相离多少像素
                - right
                - top       //离顶部相离多少像素
                - bottom 

                ----->尽量避免出现冲突的值，如果有冲突：左边大于右边，上边大于下边

       2. 特点：
           》与margin的区别在于，margin进行偏移时  为了保持内容盒的始终充满   会影响宽度的值
                               而relative：，， 只会影响便宜的位置，而不会影响宽度的值
           》盒子的偏移不会对其他盒子造成任何影响


   ### 2. 绝对定位

        1.  宽高为auto时，盒子尺寸适应内容
        2.  包含块（坐标系）变化：找祖先元素中（从临近父元素开始）的第一个定位元素，该元素的填充盒为其包含块;
                                  若找不到，则它的包含块为整个网页（初始化包含块）

   ### 3. 固定定位

        1.  其他情况与绝对定位完全一样
        2.  包含块不同：固定为视口（浏览器的可视窗口）


      ！！可视窗口指的时当前页面，无论怎样缩放始终显示的浏览器页面
          初始化包含块，指的是整个网页，其宽高等属性值的是总的父元素html



   ### 4. 定位下的居中

           1. 某个方向上的居中
                 步骤：
                     1. 定宽（高）
                     2. 将左右（上下）距离设置为0     //上下或者左右均为0时，以左边和上边的为主；
                                                     //若上面设置为0，下面没设置，浏览器将自动计算下方距离
                     3. 将左右（上下）的margin设置为auto

                         //在绝对定位和固定定位中，margin设置为auto时候，会自动吸收剩余空间
                           因为poistion的属性值：左右上下  均设置为0，为了让元素适应，只能使用元素的margin撑开网页的四面八方以适应设置


   ### 5. 多个定位元素重叠时

         堆叠上下文

         设置z-index属性（垂直坐标轴）：通常情况下，该值越大，越靠前（越靠近用户）

         只有定位元素设置z-index有效

         z-index可以设置为负数，如果是负数，则在遇到常规流、浮动元素时会被其覆盖


   6.  绝对定位、固定定位一定是块盒
       绝对定位、固定定位一定不是浮动
       没有外边距合并
             

     





## 15. 拓展


### 1. 透明度

     每个颜色都有透明通道，数值为0~1（数值越大越不透明）

     表示方法：
            1. rgba(红、绿、蓝、alpha)

            2. hex：#红绿蓝alpha
  
   




