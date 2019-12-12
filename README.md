# 目录

- [Excel Functions](#excel-functions)
    + [SUM](#sum)
    + [COUNT 系列](#count 系列)
      - [COUNT](#count)
      - [COUNTA](#counta)
      - [COUNTBLANK](#countblank)
      - [COUNTIF](#countif)
      - [COUNTIFS](#countifs)
    + [未完待续](#----)

<small><i><a href='http://ecotrust-canada.github.io/markdown-toc/'>Table of contents generated with markdown-toc</a></i></small>



# Excel Functions

### SUM

#### 函数功能

对所有参数进行求和（相加）操作，返回所有参数的和。

#### 函数定义

>  SUM(number1, [number2], ...)

#### 参数解释

+ number1
  + 必选，可以是一个数字，也可以是单元格引用；如果是文本形式的数字，会转换类型后相加。
+ number2, …
  + 可选，同number1。

#### 示例

设表格如下：

|      |  A   |
| :--: | :--: |
|  1   |  -1  |
|  2   |  1   |
|  3   | “3”  |

输入与输出示例：

> \> SUM(A1, A2)
>
> < 0

> \> SUM(A1:A3)
>
> < 3

------

### COUNT 系列

#### COUNT

##### 函数功能 

统计单元格类型为数值型的单元格数量，布尔值与日期也计入其中，空或文本型的单元格不被统计。

##### 函数定义

> COUNT(value1, [value2], …)

##### 参数解释

+ value1
  + 必选，可以是值或单元格引用。
+ value2, ...
  + 可选。

##### 示例

设表格如下：

|      |  A   |     B      |
| :--: | :--: | :--------: |
|  1   |  -1  |    TRUE    |
|  2   |  1   | 2000/06/18 |
|  3   | “1”  |            |

输入与输出示例：

> \> COUNT(A1,A2,A3)
>
> < 2

> \> COUNT(A1:B3)
>
> < 4

------

#### COUNTA

##### 函数功能

统计不为空的单元格数量。

##### 函数定义

> COUNTA(value1, [value2], …)

##### 参数解释

+ value1
  + 必选，可以是值或单元格引用。
+ value2, ...
  + 可选。

##### 示例

设表格如下：

|      |  A   |     B      |
| :--: | :--: | :--------: |
|  1   |  -1  |    TRUE    |
|  2   |  1   | 2000/06/18 |
|  3   | “1”  |            |

输入与输出示例：

> \> COUNTA(A1,A2,A3)
>
> < 3

> \> COUNTA(A1:B3)
>
> < 5

------

#### COUNTBLANK

##### 函数功能 

统计空白的单元格数量。

##### 函数定义

> COUNTBLANK(range)

##### 参数解释

+ range
  + 必选，可以是值或单元格引用。

##### 示例

设表格如下：

|      |  A   |  B   |
| :--: | :--: | :--: |
|  1   |  -1  | TRUE |
|  2   |      |      |
|  3   | “1”  |      |

输入与输出示例：

> \> COUNTBLANK(A1:B3)

> < 3

------

#### COUNTIF

##### 函数功能 

统计符合条件的单元格数量。

##### 函数定义

> COUNTIF(range, criteria)

##### 参数解释

+ range
  + 要统计的区域。
+ criteria
  + 匹配的条件。

##### 示例

设表格如下：

|      |  A   |     B      |
| :--: | :--: | :--------: |
|  1   |  -1  |   FALSE    |
|  2   |  1   | 2000/06/18 |
|  3   | “1”  |            |

输入与输出示例：

> \> COUNTIF(A1:A3, "<1")
>
> < 1

> \> COUNTIF(A1:B3, "=1")
>
> < 2

------

#### COUNTIFS

##### 函数功能 

统计符合所有条件的单元格数量。与COUNTIF不同的是，它支持多个条件，只有符合所有的条件才会被计入符合条件的单元格数量。

##### 函数定义

> COUNTIFS(criteria_range1, criteria1, [criteria_range2, criteria2], ...)

##### 参数解释

+ criteria_range1
  + 必须，应用于条件一的统计区域。
+ criteria1
  + 第一个条件，用于匹配criteria_range1。
+ criteria_range2, criteria2, ...
  + 可选，可用于匹配更多的条件。

**每一个可选的条件区域都需要有与criteria_range1相同的行数与列数**

##### 示例

设表格如下：

|      |  A   |     B      |
| :--: | :--: | :--------: |
|  1   |  -1  |     5      |
|  2   |  1   | 2000/06/18 |
|  3   | “1”  |            |

输入与输出示例：

> \> COUNTIFS(A1:A3, "=1", B1:B3, ">1")
>
> < 1
>
> > 1. 计算A1:A3中等于1的单元格，符合此条件的有A2和A3。
> >
> > 2. 计算B2:B3（去掉不符合条件一的行）中大于1的单元格，符合此条件的有B2，故返回1

------
### 未完待续
