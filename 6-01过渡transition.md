##### 一、过渡（transition）

​          \- 通过过渡可以指定一个属性发生变化时的切换方式

​          \- 通过过渡可以创建一些非常好的效果，提升用户的体验

##### 二、transition-property: 指定要执行过渡的属性  

​        多个属性间使用,隔开 

​        如果所有属性都需要过渡，则使用all关键字

​        大部分属性都支持过渡效果，注意过渡时必须是从一个有效数值向另外一个有效数值进行过渡

```css
transition-property: height , width; 
transition-property: all;
```

##### 三、transition-duration: 指定过渡效果的持续时间

​        时间单位：s 和 ms  1s = 1000ms

```css
transition-duration: 100ms, 2s;
transition-duration: 2s;
```

#####  四、transition-timing-function: 过渡的时序函数

###### 1、 指定过渡的执行的方式  

​        **可选值：**

> ​          ease 默认值，慢速开始，先加速，再减速
>
> ​          linear 匀速运动
>
> ​          ease-in 加速运动
>
> ​          ease-out 减速运动
>
> ​          ease-in-out 先加速 后减速
>
> ​          cubic-bezier() 来指定时序函数 https://cubic-bezier.com

######  2、steps() 分步执行过渡效果

​	可以设置一个第二个值：

​              end ， 在时间结束时执行过渡(默认值)

​              start ， 在时间开始时执行过渡

```css
transition-timing-function: cubic-bezier(.24,.95,.82,-0.88);
transition-timing-function: steps(2, start);
```

###### 3、transition-delay: 过渡效果的延迟，等待一段时间后在执行过渡

```css
transition-delay: 2s;
```

##### 五、简写

**transition 可以同时设置过渡相关的所有属性，只有一个要求，如果要写延迟，则两个时间中第一个是持续时间，第二个是延迟**

```css
transition:2s margin-left 1s cubic-bezier(.24,.95,.82,-0.88);
```

