[toc]

`mermaid` 支持流程图、甘特图和时序图，但是经过这次尝试，结论就是画图的话还是使用专业的画图工具，这个只能作为一种简单选项用在简单场景下。所以这里就只总结一下流程图的使用，其它两种就没必要了，不是怎么好用。

[mermaid官网](https://mermaid.js.org/intro/)

# 流程图方向

流程图总体分为横向和纵向两种。总共四个方向：T-上，B\D-下；L-左，R-右。使用方式就是横向的两两结合，纵向的两两结合。比如从左到右为LR，从上到下为TB或者TD。

从上到下演示：

```mermaid
graph TD
    A --> B
```

从左到右演示：

```mermaid
graph LR
    A --> B
```

# 流程图节点

下面展示的流程图节点有矩形 `'[]'`，圆角矩形 `'()'`，不对称矩形 `'>]'`，菱形 `'{}'`，圆形 `'(())'`。在每个节点前面需要唯一标识该节点ID。如下示例：

```mermaid
graph TD
    a1[带文本矩形]
    a2(带文本圆角矩形)
    a3>带文本不对称矩形]
    b1{带文本菱形}
    c1((带文本圆形))
```

# 节点间的连接关系

- 节点之间的连接线分为：实线 '---'、加粗实线 '==='、虚线 '-.-'。
- 带箭头的连接线分为：带箭头实线 '-->'、带箭头加粗实线 '==>'，带箭头虚线 '-.->'。
- 如果要在连接线上加上备注，则上面两类加备注的方式如下：
  - 实线备注 '--yes---'，加粗实线备注 'yes='，虚线备注 '-.yes.-'。
  - 带箭头实线备注 '--yes-->'，带箭头加粗实线备注 'yes>'，带箭头虚线备注 '-.yes.->'

其中，每种连接符号的左边是开始节点，右边是结束节点，可以由同一个节点指向不同节点，也可以由不同节点指向同一个节点，实现各种指向方式都是通过节点ID标注。

示例如下：

```mermaid
graph LR
    A10[A10] --- A11[A11]
    A20[A20] === A21[A21]
    A30[A30] -.- A31[A31]
    B10[B10] --> B11[B11]
    B20[B20] ==> B21[B21]
    B30[B30] -.-> B31[B31]
    C10[C10] --yes--> C11[C11]
    C20[C20] ==yes==> C21[C21]
    C30[C30] -.yes.-> C31[C31]
```

由同一个节点开始，使用方式如下，对于后面如果使用同一个节点，只用指明ID即可。

```mermaid
graph LR
    A[开始节点] --> B[结束节点1]
    A --> C[结束节点2]
```

# 冒泡排序流程图

在这里用一个冒泡排序来简单的练习一下上面的几个点，首先将冒泡排序的伪码粘贴上来：

```
BUBBLESORT(A)
	for i = 1 to A.length-1
		for j = A.length downto i + 1
			if A[j] < A[j - 1]
				exchange A[j] with A[j - 1]
```

演示代码如下：

```mermaid
graph TD
	start([开始]) --> 赋值arr[赋值arr]
	赋值arr --> 赋值len[len = arr.length]
	赋值len --> 赋值i[i = 0]
	赋值i --> 第一层循环{i < len}
    第一层循环 --yes--> 赋值j[j = 1]
    赋值j --> 第二层循环{"j < len - i ?"}
    第二层循环 --yes--> 判断{"arr[j - 1] < arr[j] ?"}
    判断 --yes--> 定义临时变量["int temp = arr[j - 1]"]
    定义临时变量 --> 交换aj["arr[j - 1] = arr[j]"]
    交换aj --> 交换aj-1["arr[j] = temp"]
    交换aj-1 --> j自增["j++"]
    j自增 --> 第二层循环
    判断 --no--> j自增
    第二层循环 --no--> i自增["i++"]
    i自增 --> 第一层循环
    第一层循环 --no--> endd([结束])
```

# 类图

## 类关系

```mermaid
---
title: Animal example
---
classDiagram
    note "From Duck till Zebra"
    Animal <|-- Duck
    note for Duck "can fly\ncan swim\ncan dive\ncan help in debugging"
    Animal <|-- Fish
    Animal <|-- Zebra
    Animal : +int age
    Animal : +String gender
    Animal: +isMammal()
    Animal: +mate()
    class Duck{
        +String beakColor
        +swim()
        +quack()
    }
    class Fish{
        -int sizeInFeet
        -canEat()
    }
    class Zebra{
        +bool is_wild
        +run()
    }
```

## 类成员

```mermaid
---
title: Bank example
---
classDiagram
    class BankAccount
    BankAccount : +String owner
    BankAccount : +Bigdecimal balance
    BankAccount : +deposit(amount)
    BankAccount : +withdrawal(amount)
```

# 时间线

```mermaid
timeline
    title History of Social Media Platform
    2002 : LinkedIn
    2004 : Facebook
         : Google
    2005 : Youtube
    2006 : Twitter
```

```mermaid
timeline
    title Timeline of Industrial Revolution
    section 17th-20th century
        Industry 1.0 : Machinery, Water power, Steam <br>power
        Industry 2.0 : Electricity, Internal combustion engine, Mass production
        Industry 3.0 : Electronics, Computers, Automation
    section 21st century
        Industry 4.0 : Internet, Robotics, Internet of Things
        Industry 5.0 : Artificial intelligence, Big data,3D printing
```

# XY 图表

```mermaid
---
config:
    xyChart:
        width: 900
        height: 600
    themeVariables:
        xyChart:
            titleColor: "#ff0000"
---
xychart-beta
    title "Sales Revenue"
    x-axis [jan, feb, mar, apr, may, jun, jul, aug, sep, oct, nov, dec]
    y-axis "Revenue (in $)" 4000 --> 11000
    bar [5000, 6000, 7500, 8200, 9500, 10500, 11000, 10200, 9200, 8500, 7000, 6000]
    line [5000, 6000, 7500, 8200, 9500, 10500, 11000, 10200, 9200, 8500, 7000, 6000]
```

# 时序图

## 普通时序图

```mermaid
sequenceDiagram
    Alice ->> Bob: Hello Bob, how are you?
    Bob-->>John: How about you John?
    Bob--x Alice: I am good thanks!
    Bob-x John: I am good thanks!
    Note right of John: Bob thinks a long<br/>long time, so long<br/>that the text does<br/>not fit on a row.

    Bob-->Alice: Checking with John...
    Alice->John: Yes... John, how are you?
```

## 带循环、条件的时序图

```mermaid
sequenceDiagram
    loop Daily query
        Alice->>Bob: Hello Bob, how are you?
        alt is sick
            Bob->>Alice: Not so good :(
        else is well
            Bob->>Alice: Feeling fresh like a daisy
        end

        opt Extra response
            Bob->>Alice: Thanks for asking
        end
    end
```

## 带自循环时序图

```mermaid
sequenceDiagram
    participant Alice
    participant Bob
    Alice->>John: Hello John, how are you?
    loop Healthcheck
        John->>John: Fight against hypochondria
    end
    Note right of John: Rational thoughts<br/>prevail...
    John-->>Alice: Great!
    John->>Bob: How about you?
    Bob-->>John: Jolly good!
```

# 脑图

## 简单实例

```mermaid
mindmap
  root((mindmap))
    Origins
      Long history
      ::icon(fa fa-book)
      Popularisation
        British popular psychology author Tony Buzan
    Research
      On effectiveness<br/>and features
      On Automatic creation
        Uses
            Creative techniques
            Strategic planning
            Argument mapping
    Tools
      Pen and paper
      Mermaid
```

# Git提交历史

```mermaid
---
title: Example Git diagram
---
gitGraph
   commit
   commit
   branch develop
   checkout develop
   commit
   commit
   checkout main
   merge develop
   commit
   commit
```

## 给提交自定义ID

```mermaid
gitGraph
    commit id: "Alpha"
    commit id: "Beta"
    commit id: "Gamma"
```

## 一个比较复杂的提价历史图

```mermaid
    gitGraph
       commit id: "1"
       commit id: "2"
       branch nice_feature
       checkout nice_feature
       commit id: "3"
       checkout main
       commit id: "4"
       checkout nice_feature
       branch very_nice_feature
       checkout very_nice_feature
       commit id: "5"
       checkout main
       commit id: "6"
       checkout nice_feature
       commit id: "7"
       checkout main
       merge nice_feature id: "customID" tag: "customTag" type: REVERSE
       checkout very_nice_feature
       commit id: "8"
       checkout main
       commit id: "9"
```

# 甘特图

```mermaid
gantt
    dateFormat  YYYY-MM-DD
    title       Adding GANTT diagram functionality to mermaid
    excludes    weekends
    %% (`excludes` accepts specific dates in YYYY-MM-DD format, days of the week ("sunday") or "weekends", but not the word "weekdays".)

    section A section
    Completed task            :done,    des1, 2014-01-06,2014-01-08
    Active task               :active,  des2, 2014-01-09, 3d
    Future task               :         des3, after des2, 5d
    Future task2              :         des4, after des3, 5d

    section Critical tasks
    Completed task in the critical line :crit, done, 2014-01-06,24h
    Implement parser and jison          :crit, done, after des1, 2d
    Create tests for parser             :crit, active, 3d
    Future task in critical line        :crit, 5d
    Create tests for renderer           :2d
    Add to mermaid                      :1d
    Functionality added                 :milestone, 2014-01-25, 0d

    section Documentation
    Describe gantt syntax               :active, a1, after des1, 3d
    Add gantt diagram to demo page      :after a1  , 20h
    Add another diagram to demo page    :doc1, after a1  , 48h

    section Last section
    Describe gantt syntax               :after doc1, 3d
    Add gantt diagram to demo page      :20h
    Add another diagram to demo page    :48h
```