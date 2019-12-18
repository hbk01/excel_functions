Table of Contents
=================

   * [Excel Functions](#excel-functions)
     * [SUM](#sum)
     * [COUNT 系列](#count-系列)
        * [COUNT](#count)
        * [COUNTA](#counta)
        * [COUNTBLANK](#countblank)
        * [COUNTIF](#countif)
        * [COUNTIFS](#countifs)
     * [LARGE](#large)
     * [SMALL](#small)
     * [LEN](#len)
     * [LENB](#lenb)
     * [IF](#if)
     * [LEFT](#left)
     * [RIGHT](#right)
     * [MID](#mid)
     * [VLOOKUP](#vlookup)
     * [LOOKUP](#lookup)

Created by [gh-md-toc](https://github.com/ekalinin/github-markdown-toc)
------

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
  + 必选，需要统计的区域。

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

**注意：每一个可选的条件区域都需要有与criteria_range1相同的行数与列数**

##### 示例

设表格如下：

|      |  A   |  B   |
| :--: | :--: | :--: |
|  1   |  -1  |  5   |
|  2   |  1   |  4   |
|  3   |  3   |  -2  |

输入与输出示例：

> \> COUNTIFS(A1:A3, ">0", B1:B3, "<0")
>
> < 1
>
> > 1. 计算A1:A3中大于0的单元格，符合此条件的有A2和A3。
> > 2. 此时仅计算B2:B3（去掉不符合条件一的行）中小于0的单元格，符合此条件的有B3。
> > 3. A1:A3与B1:B3中，只有第三行（A3与B3）符合各自的条件，故返回1

------
### LARGE
##### 函数功能 
在一组数据中从大到小取第几个值。
##### 函数定义
> LARGE(array, num)
##### 参数解释
+ array
  + 一组数据
+ num
  + 第几个
##### 示例
设表格如下：
|      |  A   |
| :--: | :--: |
|  1   |  3   |
|  2   |  1   |
|  3   |  2   |
|  4   |  4   |

则：
> \> LARGE(A1:A4,2)
> < 3

> \> LARGE(A1:A4,1)
> < 4

### SMALL
##### 函数功能 
在一组数据中从小到大取第几个值。
##### 函数定义
> SMALL(array, num)
##### 参数解释
+ array
  + 一组数据
+ num
  + 第几个
##### 示例
设表格如下：
|      |  A   |
| :--: | :--: |
|  1   |  3   |
|  2   |  1   |
|  3   |  2   |
|  4   |  4   |

则：
> \> SMALL(A1:A4,2)
> < 2

> \> SMALL(A1:A4,1)
> < 1

### LEN
##### 函数功能 
求字符串的长度
##### 函数定义
> LEN(text)
##### 参数解释
+ text
    + 要计算字符个数的文本
##### 示例
设表格如下：
|      |       A       |
| :--: | :-----------: |
|  1   |     A123      |
|  2   | some of excel |
|  3   |     哈哈      |

则：
> \> LEN(A1)
> < 4

> \> LEN(A2)
> < 13

> \> LEN(A3)
> < 2


### LENB
##### 函数功能 
求字符串的长度（1个中文字按2个计算）
##### 函数定义
> LEN(text)
##### 参数解释
+ text
    + 要计算字符个数的文本
##### 示例
设表格如下：
|      |       A       |
| :--: | :-----------: |
|  1   |     A123      |
|  2   | some of excel |
|  3   |     哈哈      |

则：
> \> LEN(A1)
> < 4

> \> LEN(A2)
> < 13

> \> LEN(A3)
> < 4


### IF
##### 函数功能 

根据布尔值返回不同的结果。

##### 函数定义
> IF(logical-test,value-if-true,value-if-false)
##### 参数解释
+ logical-test
    + 是布尔值的任意公式、函数等
+ value-if-true
    + 如果logical-test是true，则执行此部分
+ value-if-false
    + 如果logical-test是false，则执行此部分
##### 示例
设表格如下：
|      |       A       |
| :--: | :-----------: |
|  1   |     -1      |
|  2   |    0       |
|  3   |     1      |

则：
> \> IF(A1<0,true,false)
>
> < true
------
### LEFT

##### 函数功能

从字符串左边开始取字符

##### 函数定义

> LEFT(text,num_chars)

##### 参数解释

+ text
  + 要截取的文本
+ num_chars
  + 要截取多少个

##### 示例

|      |   A    |
| :--: | :----: |
|  1   | ABC123 |

> \> LEFT(A1,3)
>
> < ABC

------

### RIGHT
##### 函数功能

从字符串右边开始取字符

##### 函数定义

> RIGHT(text,num_chars)

##### 参数解释

+ text
  + 要截取的文本
+ num_chars
  + 要截取多少个

##### 示例

|      |   A    |
| :--: | :----: |
|  1   | ABC123 |

> \> RIGHT(A1,3)
>
> < 123

### MID
##### 函数功能 
从一个文本中提取字符串，是LEFT与RIGHT的升级版，可以从指定位置开始。
##### 函数定义
> MID(text, start_num, num_chars)
##### 参数解释
+ text
    + 要提取文本的字符串
+ start_num
    + 从哪里开始提取
+ num_chars
    + 提取多少个
##### 示例

|      |   A    |
| :--: | :----: |
|  1   | ABC123 |

> \> MID(A1,3,2)
>
> < C1


### VLOOKUP
##### 函数功能 
根据一个值去某个区域查找值
##### 函数定义
> VLOOKUP(lookup_value,table_array,col_index_num,range_lookup)
##### 参数解释
+ lookup_value
    + 要查找的值
+ table_array
    + 去哪里查找
+ col_index_num
    + 如果找到了返回第几列
+ range_lookup
    + 选择精确匹配还是模糊匹配
##### 示例
设表格如下：
|     | A   | B   | C   |
| :-: | :-: | :-: | :-: |
| 1   | 1   | 30  | 23  |
| 2   | 2   | 10  | 26  |
| 3   | 3   | 20  | 12  |
| 4   | 4   | 23  | 26  |

> \> VLOOKUP(3,A1:C4,2,false)
> < 20


### LOOKUP
##### 函数功能 
##### 函数定义
##### 参数解释
##### 示例
