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
     * [MOD](#mod)
     * [RANK.EQ](#rank.eq)
     * [未完待续](#未完待续)
   * [Excel Keymaps](#excel-keymaps)
     * [快捷键语法说明](#快捷键语法说明)
     * [快捷键](#快捷键)

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
  + 可选，同 number1。

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

------

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

统计符合所有条件的单元格数量。与 COUNTIF 不同的是，它支持多个条件，只有符合所有的条件才会被计入符合条件的单元格数量。

##### 函数定义

> COUNTIFS(criteria_range1, criteria1, [criteria_range2, criteria2], ...)

##### 参数解释

+ criteria_range1
  + 必须，应用于条件一的统计区域。
+ criteria1
  + 第一个条件，用于匹配 criteria_range1。
+ criteria_range2, criteria2, ...
  + 可选，可用于匹配更多的条件。

**注意：每一个可选的条件区域都需要有与 criteria_range1 相同的行数与列数**

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
> > 1. 计算 A1:A3 中大于 0 的单元格，符合此条件的有 A2 和 A3。
> >
> > 2. 此时仅计算 B2:B3（去掉不符合条件一的行）中小于 0 的单元格，符合此条件的有 B3。
> >
> > 3. A1:A3 与 B1:B3 中，只有第三行（A3 与 B3）符合各自的条件，故返回 1
>

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
>
> < 3

> \> LARGE(A1:A4,1)
>
> < 4

------

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
>
> < 2

> \> SMALL(A1:A4,1)
>
> < 1

------

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

|      | A             |
| :--: | :-----------: |
| 1    | A123          |
| 2    | some of excel |
| 3    | 哈哈          |

则：
> \> LEN(A1)
>
> < 4

> \> LEN(A2)
>
> < 13

> \> LEN(A3)
>
> < 2

------

### LENB

##### 函数功能

求字符串的长度（1 个中文字按 2 个计算）

##### 函数定义

> LENB(text)

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
> \> LENB(A1)
>
> < 4

> \> LENB(A2)
>
> < 13

> \> LENB(A3)
>
> < 4

------

### IF

##### 函数功能

根据布尔值返回不同的结果。

##### 函数定义

> IF(logical_test,value_if_true,value_if_false)

##### 参数解释

+ logical_test
    + 是布尔值的任意公式、函数等
+ value_if_true
    + 如果 logical_test 是 true，则执行此部分
+ value_if_false
    + 如果 logical_test 是 false，则执行此部分

##### 示例

设表格如下：

|      | A   |
| :--: | :-: |
| 1    | -1  |
| 2    | 0   |
| 3    | 1   |

> \> IF(A1<0,true,false)
>
> < true

------

### LEFT

##### 函数功能

从文本的左边开始提取字符

##### 函数定义

> LEFT(text,num_chars)

##### 参数解释

+ text
  + 要提取的文本
+ num_chars
  + 要提取多少个

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

从文本的右边开始提取字符

##### 函数定义

> RIGHT(text,num_chars)

##### 参数解释

+ text
  + 要提取的文本
+ num_chars
  + 要提取多少个

##### 示例

|      |   A    |
| :--: | :----: |
|  1   | ABC123 |

> \> RIGHT(A1,3)
>
> < 123

------

### MID

##### 函数功能

从一个文本中提取字符串，可以从指定位置开始。

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

|      | A      |
| :--: | :----: |
| 1    | ABC123 |

> \> MID(A1,3,2)
>
> < C1

------

### VLOOKUP

##### 函数功能

根据一个值去某个区域查找值并返回指定的列。

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
>
> < 20

------

### LOOKUP

##### 函数功能

返回向量或数组中的数值。LOOKUP 有两种形式，向量形式为单行或单列中查找数值，返回另一个单行或单列区域中相同位置的数值。数组形式为，在数组的第一行或第一列查找数值，返回数组的最后一行或一列中相同位置的数值。

##### 函数定义

> LOOKUP(lookup_value,lookup_vector,result_vector)
>
> LOOKUP(lookup_value,array)

##### 参数解释

+ lookup_value
    + 要查找的值
+ 向量形式
    + lookup_vector
        + 只包含一行或一列的区域
    + result_vector
        + 只包含一行或一列的区域，大小必须与 lookup_vector 一致
+ 数组形式
    + array
        + 数组，从数组的第一行或第一列查找数据，返回数组最后一行或最后一列中相同位置的数据。

**注意：不论是数组形式还是向量形式，第二个参数必须是按升序排列，否则可能无法返回正确的值**

##### 示例

|     | A   | B    |
| :-: | :-: | :--: |
| 1   | 3   | 15   |
| 2   | 4   | 34   |
| 3   | 5   | 23   |
| 4   | 6   | 35   |

> \> LOOKUP(5,A1:B4)
>
> < 23
>
> \> LOOKUP(3,A1:A4,B1:B4)
>
> < 15

------

### MOD

##### 函数功能

取余数

##### 函数定义

> MOD(number,divisor)

##### 参数解释

+ number
    + 被除数
+ divisor
    + 除数

##### 示例

> \> MOD(10,2)
>
> < 0

------

### RANK.EQ

##### 函数功能

获取一个数字在一组数据中的排名

##### 函数定义

> RANK.EQ(number,ref,order)

##### 参数解释

+ number
    + 指定的数字
+ ref
    + 一组数据，非数字的值会被忽略
+ order
    + 指定排序方式，0 或忽略为降序，非零为升序

##### 示例

|   |  A |
|:-:|:--:|
| 1 | 23 |
| 2 | 42 |
| 3 | 32 |
| 4 | 12 |
| 5 | 63 |

> \> RANK.EQ(A5,A1:A5)
>
> < 1

------

### 未完待续

------

# Excel Keymaps

### 快捷键语法说明

定义一下语法，不会显得太过累赘。

快捷键写在 \<\> 中。

| 语法 |      说明      |
|:----:|:--------------:|
|   c  |      ctrl      |
|   a  |       alt      |
|   C  |   ctrl+shift   |
|   A  |    alt+shift   |
|   F  | 功能键（如 F1）|
|   -  |     分隔符     |

如：

> `<c-a>` ctrl+a
>
> `<C-a>` ctrl+shift+a
>
> `<CA-a>` ctrl+alt+shift+a
>
> `<ca-a>` ctrl+alt+a
>

------

### 快捷键

| 快捷键      | 功能                                               |
|:------------|:---------------------------------------------------|
| \<C-down\>  | 快速选择光标下的一列，其他方向键同此功能           |
| \<c-down\>  | 快速把光标定位到最下，其他方向键同此功能           |
| \<F9\>      | 在公式栏中选择一段公式，按 F9 可计算选择的公式     |
| \<F4\>      | 公式栏中光标放到单元格引用上，按 F4 可切换绝对引用 |
| \<C-enter\> | 将此公式作为数组确定，此时不可以使用平时的确认方法 |
| \<c-home\>  | 快速定位到 A1 单元格                               |
| \<a-enter\> | 强制换行                                           |
| \<c-1\>     | 打开单元格格式对话框                               |
