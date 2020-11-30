# EXCEL数据处理方法汇总

### 文本处理函数

#### Trim函数

1. 作用：除了单词之间的单个空格外，移除文本中的所有空格
2. 语法：Trim\(text\)，其中Text为必需项，为要移除空格的文本

![](.gitbook/assets/image%20%281%29.png)

#### Concatenate函数

1. 作用：将两个或多个文本字符串联接为一个字符串
2. 语法：CONCATENATE\(text1, \[text2\], ...\)，至少包含一个项目，最多255个项目，最多支持8192个字符，项目可以是文本值、数字、或单元格引用。
3. 说明：可以利用连接符&实现相同的功能

![](.gitbook/assets/image%20%282%29.png)

#### Replace函数

1. 作用：将特定位置的字符串替换为不同的文本字符
2. 语法：REPLACE\(old\_text, start\_num, num\_chars, new\_text\)，old\_text为需要替换的文本，start\_num替换字符的位置，num\_chars利用new\_text替换的字符数，new\_text要替换old\_text的新文本。
3. 例子：在如下的例子中，便将apple的第2个字符（p）起，连续三个字符（ppl）替换为@

![](.gitbook/assets/image%20%284%29.png)

#### Substitue函数

1. 作用：在某一文本字符串中替换指定的文本
2. 语法：SUBSTITUTE\(text, old\_text, new\_text, \[instance\_num\]\)，text为包含需要替换的文本，old\_text为需要替换的文本，new\_text为替换old\_text的文本，instance\_num为可选参数，指定了数字则只替换相应顺序的old\_text，否则全部替换
3. 和Replace函数的区别：Substitue根据文本内容进行替换，Replace根据字符位置进行替换

![](.gitbook/assets/image%20%285%29.png)

#### 三种提取字符的函数（LEFT函数、RIGHT函数以及MID函数）

* LEFT函数，从文本字符串的第一个字符开始返回指定个数的字符；LEFT\(text, \[num\_chars\]\)，text包含要提取的字符，num\_chars为指定要提取的字符数量，必须≥0，如果大于文本长度，则返回全部文本，如果省略则假定其值为1
* RIGHT函数，用法同Left，只是取数方向相反，从右侧开始取数
* MID函数，从指定位置开始提取特定数目的字符；MID\(text, start\_num, num\_chars\)，text包含要提取字符的文本，start\_num文本中要提取第一个字符的位置，num\_chars希望提取的字符个数

![](.gitbook/assets/image%20%2810%29.png)

### 信息反馈函数

#### Exact函数

1. 作用：比较两个文本字符串，如果它们完全相同，则返回 TRUE，否则返回 FALSE。 函数 EXACT 区分大小写，但忽略格式上的差异。 使用 EXACT 可以检验在文档中输入的文本。
2. 语法：EXACT\(text1, text2\)，text1和text2两个需要比较的字符串

#### IS函数

作用： 此类函数可检验指定值并根据结果返回 TRUE 或 FALSE。 在对某一值执行计算或执行其他操作之前，可以使用 **IS** 函数获取该值的相关信息

![](.gitbook/assets/image%20%287%29.png)

### 查找引用函数

#### Vlookup函数

1. 作用：在表格区域中按行查找对应内容
2. 语法：VLOOKUP（要查找的值，要在其中查找值的区域，区域中包含返回值的列号，精确匹配或近似匹配 – 指定为 0/FALSE 或 1/TRUE）
3. 注意事项：要查找的值需要始终位于所在区域的第一列
4. 例子，在如下的例子中，要查找的值在第E列（name为孙、李、我），要查找的区域为name列和score列，若查找成功，则返回查找区域的第2列（即score），从而实现这样一个不同表的score匹配（因为要查找的值和查找区域可以分别在两个sheet或excel表中）

![](.gitbook/assets/image%20%289%29.png)

#### Hlookup函数

1. 作用：在表格中按列查找对应内容
2. 语法：HLOOKUP\(lookup\_value, table\_array, row\_index\_num, \[range\_lookup\]\)，参数和VLOOKUP相对应，第三个参数为行号，VLOOKUP第三个参数为列号。
3. 例子：在A1：D4区域内，查找G1（D），返回A1：D4区域内第2行的结果。

![](.gitbook/assets/image%20%283%29.png)

### 逻辑运算函数

#### If函数：

1. 作用：对值和期待值进行逻辑比较
2. 语法：IF\(logical\_test, value\_if\_true, \[value\_if\_false\]\)，当logical\_test成立时，返回value\_if\_true，当logical\_test不成立时，返回value\_if\_false。IF函数最多嵌套64个。
3. 例子：如果当A2=3时，则显示may

![](.gitbook/assets/image%20%288%29.png)

### 数学统计函数

#### Sum函数：

1. 作用：可以将单个值、单元格引用或是区域相加，或者将三者的组合相加
2. 语法：SUM\(number1,\[number2\],...\)

#### Sumif函数：

1. 作用：对符合条件的值求和，例如，对B2~B25单元格大于5的值求和，可以使用公式=SUMIF\(B2:B25,"&gt;5"\)
2. 语法：SUMIF\(range, criteria,\[sum\_range\]\)，range为需要计算的区域，字符数不能超过255个；criteria求和的条件，可以使用通配符？和\*；sun\_range为可选条件，指定实际求和的区域。
3. 例子：对C列（school）中为高中的学生进行D列（score）求和。

![](.gitbook/assets/image%20%2814%29.png)

#### Sumifs函数：

1. 作用：用于计算其满足多个条件的全部参数的总量
2. 语法：SUMIFS\(sum\_range, criteria\_range1, criteria1, \[criteria\_range2, criteria2\], ...\) ，sum\_range要求和的区域，criteria\_range1为条件区域1，criteria1为对区域1进行条件限定的条件1，之后的参数以此类推。

#### Count函数

1. 作用：计算包含数字的单元格个数以及参数列表中数字的个数
2. 语法：COUNT\(value1, \[value2\], ...\)，value1为要计算数字个数的第一项、单元格应用或区域，value2可选参数，作用同value1
3. 说明：参数为数字、日期、代表数字的文本（如“1”）、逻辑值和直接键入参数列表中的数字将被计算在内

![](.gitbook/assets/image%20%2813%29.png)

#### Countif函数

1. 作用：用于统计满足某个条件的单元格的数量
2. 语法：COUNTIF\(range,criteria\)，类似SUMIF初级使用方法

![](.gitbook/assets/image%20%2811%29.png)

#### Countifs函数

1. 作用：将条件应用于跨多个区域的单元格，然后统计满足所有条件的次数
2. 语法：COUNTIFS\(criteria\_range1, criteria1, \[criteria\_range2, criteria2\],…\)，criteria\_range1为条件区域1，criteria1为对criteria\_range1指定的限定条件1，其他以此类推。

#### Counta函数

1. 作用：计算不为空的单元格的个数
2. 语法：COUNTA\(value1, \[value2\], ...\)，value1表示要计数区域，value2可选参数，作用同value1

#### Countblank函数

用法：COUNTBLANK（range）计算选中区域的空单元格个数

#### Rank函数

1. 用法：返回一列数字的数字排位， 数字的排位是其相对于列表中其他值的大小
2. 语法：RANK\(number,ref,\[order\]\)，number需要排位的数字；ref数字排列的数组；order可选参数，=0或省略降序排列，=不为零升序排列。













