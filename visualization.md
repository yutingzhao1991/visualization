数据可视化系统的抽象
===

如何选择可视化模型（图表）
---

上一段说了数据的需求需要是能够归纳的，能够模块化的。具体到产品设计的时候则需要将这些可归纳的需求奢易一个对应的数据可视化模型，这个模型可能是一个图，也可能是一张表，或者是一些文字信息，也有可能是他们之间的组合。关于数据可视化模型的选择，其实最基本的也就是对一些基础图表的选择。比如说应该用饼图还是柱状图等等。关于这一点可以参考我之前看到的一篇博客[《阮一峰的网络日志 数据可视化：基本图表》](http://www.ruanyifeng.com/blog/2014/11/basic-charts.html)。

这篇博客最开始的序言我很认可：

> 进入正题之前，先纠正一种误解。
有人觉得，基本图表太简单、太原始，不高端，不大气，因此追求更复杂的图表。但是，越简单的图表，越容易理解，而快速易懂地理解数据，不正是"数据可视化"的最重要目的和最高追求吗？
> 所以，请不要小看这些基本图表。因为用户最熟悉它们，所以只要是适用的场合，就应该考虑优先使用。

正如我在上一部分所说，web前端的可交互性最终也是为了服务于数据需求，千万不要一味的迷恋复杂的交互。要从实际的需求出发，选择最适合的方案，而不是最炫酷的方案。

关于基本图表的选择我参考这篇博客整理如下：

- 柱状图：由于肉眼对高度很敏感，所以很适合用于对数据的对比。
- 折线图：折线图适合二维的大数据集，尤其是那些趋势比单个数据点更重要的场合。
- 饼图：饼图是一种应该避免使用的图表，因为肉眼对面积大小不敏感。一般情况下，总是应该用柱状图替代饼图。但是有一个例外，就是反映某个部分占整体的比重，比如贫穷人口占总人口的百分比。一般情况下，总是应该用柱状图替代饼图。但是有一个例外，就是反映某个部分占整体的比重，比如贫穷人口占总人口的百分比。
- 散点图：散点图适用于三维数据集，但其中只有两维需要比较。
- 气泡图：气泡图是散点图的一种变体，通过每个点的面积大小，反映第三维。
- 雷达图：雷达图适用于多维数据（四维以上），且每个维度必须可以排序（国籍就不可以排序）。但是，它有一个局限，就是数据点最多6个，否则无法辨别，因此适用场合有限。

这些基础的图表的选择参考是当我们在选择最基础的展示形式的时候的依据，但是事实上并没有这么简单。这两年伴随大数据的发展，数据的需求也越来越复杂，对数据可视化站点的要求也越来越高。通常对于一个数据可视化的模块都是由多个数据可视化的组件构成的，然而每个数据可视化的组件可能是一个也可能是多个图表共同构成的。所以除了需要选择最基础的图表以外，还需要设计这些图表上层的模块，使得这些图表能够有机的结合气来。