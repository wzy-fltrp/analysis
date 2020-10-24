# 序言

这是两个满足一定规律的常见数列：

$$
\overbrace{1,\dots}^{n个}
\\\overbrace{1,2,\dots}^{n个}
$$

根据第一个数列的形式，能否看出这个数列所满足的规律是什么，是1,2,3,4...，1,3,5,7...还是1,4,9...，应该是很难看出来的吧；那根据第二个数列的形式，来个简单的判断，是1,2,3,4...还是1,2,4,8...，是否也是比较难判断的，但相较而言，我们最起码能排除1,3,5,7...还有1,4,9...这种类型的规律了；这样来看，如果将这个问题变成ABCD四个选项的选择题，第二个数列答（猜）对的概率是不是就更大了些；

同时换一个更简单问题，这两个数列的第三个数是多少？第一个数列的第三个数为3,5还是9，第二个数列的第三个数为3还是4；显而易见，实际上提供的信息越多，也能越将答案约束在一个范围中。

{% hint style="info" %}
提供的信息越多，能够排除的错误选项越多，这样的话，得到正确答案的概率也就会越大。
{% endhint %}

无论统计学这一学科，或者是数据分析、数据挖掘这些方法，实质都和概率有着密切的关系，所得到的结论也大多也不是很直接，举个例子，两个符合正态分布的变量之间的Pearson度量结果（或者说一致性）为0.001，也不能直接说两者毫无关系，只是不存在或存在较弱的线性相关关系，可能存在某些函数关系；而对于目前比较热门的DeepLearning方法，神经元的输出值也只是选取一个较大概率的输出结果进行输出。

因此，既然这些方法都和概率有关，那么如何提高这些方法的准确性呢，根据所提的两个问题，应用一个数据分析实例中，主要有以下几点：

* 用大样本数据预测小样本数据；可以看第一个数列，分别预测第二个数和第三个数，预测那个数的误差会大些呢；但是试想，如果有人能用小样本数据预测小样本数据，即用一天各个时刻的数据能预测接下来一个月的数据，那用一个月中每天的数据肯定也能预测一年的数据，用一年中每个月的数据也就能预测未来30年的数据，那也太厉害了吧；
* 提供更多的样本量；上面一直在说所提到的信息是什么呢，我认为和样本量的数量有关，样本量越多，所包含的信息也就越多；在一个教育测量任务中，样本量也就等同于被测学生的数量，可能对于我来说，更主要的是被测学生的数量，这些也是可以进行把控的，如果选择限制被测学生的数量，而增添题目的数量，是否还要考虑测试时间过长，引起学生反感的因素，这些因素实际上是无法进行度量分析；
* 循序渐进的数据查看、分析、挖掘流程；这部分不用在序言中细讲

