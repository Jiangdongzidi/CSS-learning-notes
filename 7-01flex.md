#### 一、flex(弹性盒、伸缩盒)

1、 是CSS中的又一种布局手段，它主要用来代替浮动来完成页面的布局

2、flex可以使元素具有弹性，让元素可以跟随页面的大小的改变而改变

3、弹性容器

​       （1） 要使用弹性盒，必须先将一个元素设置为弹性容器

​       （2）我们通过 display 来设置弹性容器

​         	 display:flex  设置为块级弹性容器

​         	 display:inline-flex 设置为行内的弹性容器

4、弹性元素

​        （1）弹性容器的子元素是弹性元素（弹性项）

​        （2）弹性元素可以同时是弹性容器

#### 二、flex-direction （主轴、辅轴）

**flex-direction 指定容器中弹性元素的排列方式**  

​	**可选值：**

​          row **默认值**，弹性元素在容器中水平排列（主轴自左向右）

​          row-reverse 弹性元素在容器中反向水平排列（主轴自右向左）

​          column 弹性元素纵向排列（自上向下）

​          column-reverse 弹性元素方向纵向排列（自下向上）

​     **主轴：**

​          弹性元素的排列方向称为主轴

​     **侧轴：**

​          与主轴垂直方向的称为侧轴

```css
 flex-direction: row;
```

#### 三、弹性元素的属性：

##### （一）flex-grow 指定弹性元素的伸展的系数

​          \- 当父元素有多余空间的时，子元素如何伸展

​          \- 父元素的剩余空间，会按照比例进行分配

##### （二）flex-shrink 指定弹性元素的收缩系数

​          \- 当父元素中的空间不足以容纳所有的子元素时，如果对子元素进行收缩

```css
 /* flex-grow: 1; */
flex-shrink: 0;
```

```html
<ul>
         <li>1</li>
         <li>2</li>
         <li>3</li>
     </ul>
```

```css
  ul{
            width: 800px;
            /* width: 300px; */
            border: 10px red solid;
            display: flex;
            flex-direction: row;
	}
 li:nth-child(1){
            flex-grow: 0;
            /* flex-shrink: 1; */
        }

        li:nth-child(2){
            background-color: pink;
            flex-grow: 2;
            /* flex-shrink: 2; */
        }

        li:nth-child(3){
            background-color: orange;
            flex-grow: 3;
            /* flex-shrink: 3; */
}
```

![image-20220705102836140](https://typora-bucket21.oss-cn-guangzhou.aliyuncs.com/note_images/image-20220705102836140.png)

![image-20220705102954091](https://typora-bucket21.oss-cn-guangzhou.aliyuncs.com/note_images/image-20220705102954091.png)

#### 四、弹性容器的样式

##### （一）flex-wrap: 元素自动换行

设置弹性元素是否在弹性容器中自动换行

###### （1）可选值：

​          nowrap 默认值，元素不会自动换行

​          wrap 元素沿着辅轴方向自动换行

​          wrap-reverse 元素沿着辅轴反方向换行

###### （2）简写：flex-flow

​		  flex-flow:  wrap 和 direction 的简写属性

```css
 flex-flow: row wrap;
```

##### （二）justify-content：主轴元素排列

如何分配主轴上的空白空间（主轴上的元素如何排列）

​        **可选值：**

​            flex-start 元素沿着主轴起边排列

​            flex-end 元素沿着主轴终边排列

​            center 元素居中排列

​            space-around 空白分布到元素两侧

​            space-between 空白均匀分布到元素间

​            space-evenly 空白分布到元素的单侧

```css
 justify-content: center;
```

##### （三）align-items: 元素辅轴对其

元素在辅轴上如何对齐

###### （1）  **可选值：**

​            stretch 默认值，将元素的长度设置为相同的值

​            flex-start 元素不会拉伸，沿着辅轴起边对齐

​            flex-end 沿着辅轴的终边对齐

​            center 居中对齐

​            baseline 基线对齐

```css
 align-items: flex-start;
```

###### （2）align-content: 辅轴空白空间的分布

```css
align-content: space-between;
```

#### 五、弹性元素的样式

##### （一）flex-grow: 1;

##### （二）flex-shrink: 1;

##### （三）flex-basis：元素基础长度

 flex-basis 指定的是元素在主轴上的基础长度

​          如果主轴是 横向的 则 该值指定的就是元素的宽度

​          如果主轴是 纵向的 则 该值指定的是就是元素的高度

​          \- 默认值是 auto，表示参考元素自身的高度或宽度

​          \- 如果传递了一个具体的数值，则以该值为准

```css
flex-basis: auto;
```

![image-20220705110502709](https://typora-bucket21.oss-cn-guangzhou.aliyuncs.com/note_images/image-20220705110502709.png)

##### （四）简写：flex 增长 缩减 基础;

 flex 可以设置弹性元素所有的三个样式

​          flex 增长 缩减 基础;

​            initial   "flex: 0 1 auto".

​            auto     "flex: 1 1 auto"

​            none    "flex: 0 0 auto" 弹性元素没有弹性

```css
 flex: initial;
```

##### （五）order ：弹性元素排列顺序

order 决定弹性元素的排列顺序

```css
 li:nth-child(1){
            order: 2;
        }

        li:nth-child(2){
            background-color: pink;  
            order: 3;
        }

        li:nth-child(3){
            background-color: orange;
            order: 1;
 }
```

![image-20220705105232877](https://typora-bucket21.oss-cn-guangzhou.aliyuncs.com/note_images/image-20220705105232877.png)