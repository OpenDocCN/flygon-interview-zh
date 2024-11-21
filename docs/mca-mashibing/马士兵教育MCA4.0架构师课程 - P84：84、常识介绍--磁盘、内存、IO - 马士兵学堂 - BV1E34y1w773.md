# 马士兵教育MCA4.0架构师课程 - P84：84、常识介绍--磁盘、内存、IO - 马士兵学堂 - BV1E34y1w773

![](img/a7b849be6d64340e7aaa2de1d8f925fe_0.png)

有一些常识。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_2.png)

常识常识是什么意思，常识不是你该炫耀的知识点，常识你必须要知道的。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_4.png)

但是在这呢我们统一来说一下这个常识，就是首先在计算机当中。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_6.png)

数据是存在磁盘，数据在磁盘里的。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_8.png)

那么以磁盘的维度，它有两个指标，第一个是寻址。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_10.png)

寻址的速度是毫秒级的，然后第二一个是带宽。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_12.png)

也就是说单位时间可以有多少个字节流过去。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_14.png)

多大的力量流过去，然后基本上是G或者照这种级别啊。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_16.png)

就是多少G或多少兆，几百兆或者12G这么这样一个一个带宽速度。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_18.png)

这是磁盘带来这样的一个一个基础知识。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_20.png)

另外一个就是内存，内存它有一个寻址。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_22.png)

![](img/a7b849be6d64340e7aaa2de1d8f925fe_23.png)

它的寻址是纳秒。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_25.png)

十纳秒，那么秒这个时间单位里边秒。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_27.png)

然后再往下小是毫秒，然后再往下小是微秒。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_29.png)

微秒，再往下小是纳秒。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_31.png)

这应该都知道。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_33.png)

所以你现在得出一个基本的常识，就是磁盘在磁盘中获取数据的时候。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_35.png)

它是毫米级很慢，然后但是在那个数据如果在内存里的话。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_37.png)

找到它，把它放到C盘计算，一定会很快就进了一个常识。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_39.png)

磁盘比内存慢了10万倍，在选址上。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_41.png)

慢了10万倍。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_43.png)

大家注意啊，是寻址，寻址上是寻址上慢了10万倍。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_45.png)

后面还会出一个小的知识点，然后内存的带宽。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_47.png)

内存里面数据完走这个带宽一定会很高，就是它的带宽。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_49.png)

带宽多大，我忘了。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_51.png)

但是一定会很大很大，因为内存就直接怼到我们这个CPU去计算，他直接走的那个数据的CPU的前端总线。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_53.png)

所以他无论怎么样，内存各种数据只在内存里。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_55.png)

各种优势是优于我们磁盘的，然后还有一个小常识没有讲过的小常识。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_57.png)

还有一个小常识就是I/O buffer。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_59.png)

I/O buffer是什么意思，我就用了一个buffer。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_61.png)

我就用了一个buffer，首先其实这是一个成本问题，什么叫成本问题。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_63.png)

磁盘有扇区。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_65.png)

磁道和扇区磁道磁道。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_67.png)

和扇区。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_69.png)

那么移山区一扇区多少字节。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_71.png)

是不是512个字节。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_73.png)

这应该是基础常识，这都是基础常识，那么这个时候注意有一个成本问题。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_75.png)

什么叫成本问题，如果我们访问一个硬盘，这个硬件的时候都是最小力度。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_77.png)

以一个扇区一个512来找。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_79.png)

那么一块硬盘是不是1T2T，是不是会有很多512，那么每一个512在哪呢。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_81.png)

我的数据在哪，一个512的那个里面放着呢。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_83.png)

那么这样你要明白一个点，就是如果容器就是一个区域足够小。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_85.png)

那么它一定带来一个成本。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_87.png)

成本变大，什么成本变大。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_89.png)

索引，也就是你如果用，如果一个1T里面都是512。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_91.png)

这么一个一个一个小格子，小格子小格子的话。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_93.png)

那么你上你上层操作系统当中的准备一个索引，这个索引就不是四个字节了。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_95.png)

可能得八个字节或者很多个字节，它一个能表示一个很很大的一个数的一个区间。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_97.png)

才能索引出这么多的512个小格子。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_99.png)

所以成本会变大，所以会变大，这所以造造就了一个东西。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_101.png)

就是在我们格式化磁盘的时候有一个4K对齐，对不对，是不是会有一个4K对齐。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_103.png)

也就是硬件的时候，并不是按照512个字节为一次读写量。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_105.png)

他会把这个变得更大一点，你读一个字节。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_107.png)

读百一十二，读1K他给到硬盘了，硬盘都是咣当给你返回4K。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_109.png)

它是如果你看512跟4K就差了很大，它俩大小就不一样了，那么一个硬盘512很多小点点。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_111.png)

4K可能点会变少，那么这时候其实索引的体量大小就会随着变化。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_113.png)

所以一般磁盘都是4K为，默认我们格式化4K操作系统。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_115.png)

操作系统。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_117.png)

无论你。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_119.png)

读多少都是最少4K。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_121.png)

从磁盘哪都是最早从从磁盘拿这个这个这个事。

![](img/a7b849be6d64340e7aaa2de1d8f925fe_123.png)

这个知识点。