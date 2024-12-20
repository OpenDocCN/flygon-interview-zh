# 系列 3：P34：【多线程与高并发】LongAdder - 马士兵_马小雨 - BV1zh411H79h

必须也得加锁对吧，你不加锁，你是完成不了这种原则性操作的，所以说你还是需要加水啊，我们讲的是呢，他讲的是他背后，你执行这条语句的背后的原理吗，这就是c a s的原理，它不需要加锁。

但其实呢它是需要靠cpu的原理来实现，好吧嗯a q s我们还没讲到啊，我们今天呢开始讲呃，继续讲一个atomic的问题，然后呢，我们开始讲除synchronized之外的别的锁，在前面的内容呢。

我们讲了synchronized，讲了volatile，讲了atomic和cs呃。

![](img/c10a0ef9c5bb66130b1f7a78c18ef634_1.png)

但是atomic呢我们只讲了一个开头，还没有讲完，今天呢我们继续。

![](img/c10a0ef9c5bb66130b1f7a78c18ef634_3.png)

好看这里啊，专门en就像原来的我们写m加加呀，就这一类的，你必须得都得加锁，如果在多线程访问的情况下，那现在呢我可以用aa omic energy了，它内部就已经也帮我们实现了原子操作。



![](img/c10a0ef9c5bb66130b1f7a78c18ef634_5.png)

原则操作是怎么做的呢。

![](img/c10a0ef9c5bb66130b1f7a78c18ef634_7.png)

直接写count their increment and get啊，这个就相当于cd加加，原来我们对抗加是需要加锁的。



![](img/c10a0ef9c5bb66130b1f7a78c18ef634_9.png)

不然的话呢会出问题，现在呢就不需要加锁了。

![](img/c10a0ef9c5bb66130b1f7a78c18ef634_11.png)

好。

![](img/c10a0ef9c5bb66130b1f7a78c18ef634_13.png)

就是m加加这块儿啊。

![](img/c10a0ef9c5bb66130b1f7a78c18ef634_15.png)

就再不需要加锁了，m加加这块不需要加锁的话呃，那么。

![](img/c10a0ef9c5bb66130b1f7a78c18ef634_17.png)

效率上呢应该来讲呢是要高一些啊，这个我再说一下啊，现在呢我模拟了，我们先读一下小程序啊，现在这个模拟了一个，像原来啊我们要记一个数，就是所有的线程都共同访问这个数，count count值呃。

大家知道当我们所有的线程都选，都要访问这个数的时候，如果每个线程给它加了个1万，往上加1万，你这时候是需要加锁的，如果你不加锁，它会出问题，上一节课呢已经演示过了。

但是如果你把它改成a term editor之后，那么你往上加呢，你就不需要再对这个cm加加，来进行加锁了啊，为什么呢，因为increment and get内部用了cs操作，直接无锁的操作往上递增。



![](img/c10a0ef9c5bb66130b1f7a78c18ef634_19.png)

那有同学可能会讲，老师他为什么要用无所操作，很简单。

![](img/c10a0ef9c5bb66130b1f7a78c18ef634_21.png)

无所操作的效率会更高，就这么简单来追求效率呢。

![](img/c10a0ef9c5bb66130b1f7a78c18ef634_23.png)

那怎么才能证明效率更高呢，来我们来看一下这个小程序啊。

![](img/c10a0ef9c5bb66130b1f7a78c18ef634_25.png)

我尝试着写了。

![](img/c10a0ef9c5bb66130b1f7a78c18ef634_27.png)

这叫抗的一可能会比较好，the factory name改成的名字，改成叫count嗯嗯。

![](img/c10a0ef9c5bb66130b1f7a78c18ef634_29.png)

扣个一啊。

![](img/c10a0ef9c5bb66130b1f7a78c18ef634_31.png)

ok，大家看这里啊，我呢，effect，我呢做了三个不同的操作，这是一个很粗糙的一个测试，但是这个测试呢，基本上也能说明一定的问题，好大家看这里，这里呢有几个比较好玩的，就是我现在模拟了很多个线程。

对一个数进行递增，好很多县城对一个数据进行递增，我们现在至少我们学的两种方法，第一种呢是我们这个long类型的数，然后对它递增的时候我们加锁，这是第一种，第二种呢是我们可以使用atomic long。

可以让它不断的往上递增，这是第二种，其实还有一种呢叫long added，由于呢很多县城对一个数进行递增。



![](img/c10a0ef9c5bb66130b1f7a78c18ef634_33.png)

这件事其实在实际我们工作之中，经常的可能会碰上。

![](img/c10a0ef9c5bb66130b1f7a78c18ef634_35.png)

所以在这种时候，你比如说秒杀秒杀的情形，我给你举个最简单，例如秒杀的情形，非常有可能会碰上，所以呢他写了好几个类来实现这种功能，那么其中一个呢叫做long adder，我们呢反正我是遇见这种东西的时候。

我会非常的好奇，我说到底是这种方式效率更高，还是说h m long效率更高，还说long adder效率更高，其实很多人的测试来看呢，这个atomic law呢很多时候也未必能比得上。

synchronized law，但是从我的测试来看，起码在现在的这种测试条件下，这tml它的效率还是要比呃synchronize要高，什么意思啊，我们来看程序。

我们count 1 count 2和count 3。

![](img/c10a0ef9c5bb66130b1f7a78c18ef634_37.png)

分别呢是三种不同的方式来实现的递增。

![](img/c10a0ef9c5bb66130b1f7a78c18ef634_39.png)

第一种呢是atomic long，第二种呢是直接synchronized的，第三种呢是用long adder。



![](img/c10a0ef9c5bb66130b1f7a78c18ef634_41.png)

long either的话，我们一会再聊好，大家看这里呃。

![](img/c10a0ef9c5bb66130b1f7a78c18ef634_43.png)

上来我起了1000个线程，线程数比较多，因为线程数太少的话呢，有好多时候你模拟不了那么高的并发，我来了1000个线程，这间的建成呢。



![](img/c10a0ef9c5bb66130b1f7a78c18ef634_45.png)

嗯现在呢我们第一步是试的是这个atomic，就是atomic la的方法啊，他是怎么做的呢。

![](img/c10a0ef9c5bb66130b1f7a78c18ef634_47.png)

一个线程的每个线程都列出来，列出来之后呢，每一个县城都做了10万次递增，每个县城都做了10万次好吧，这是第一种方式啊，然后我打印它开始了是吧，等它呃，打印骑士时间，等线程开始，等所有线程结束。

打印结束时间，算一下最后花了多少时间，这是因为最基础的测试，就是因为呢这个这种测试呢太粗糙，所以我才想说我们在这个包里呢。



![](img/c10a0ef9c5bb66130b1f7a78c18ef634_49.png)

我给大家讲一下，gmh那种测试呢相对更加的科学一些。

![](img/c10a0ef9c5bb66130b1f7a78c18ef634_51.png)

嗯后面讲到的时候，我们再来聊这个问题，就是更加专业的那种性能上的测试，那好这是第一种方式，那么第二种方式是什么呢。



![](img/c10a0ef9c5bb66130b1f7a78c18ef634_53.png)

第二种方式是我用ciront，用一个lock object log等于用object等于new random，依然是一样的，只不过这次呢在递增的时候。



![](img/c10a0ef9c5bb66130b1f7a78c18ef634_55.png)

我是写的是sront lock，所以这里是替代了atomic la。

![](img/c10a0ef9c5bb66130b1f7a78c18ef634_57.png)

上面是atomic law，下面是synchronized log，同样的计算时间，这就不说了。

![](img/c10a0ef9c5bb66130b1f7a78c18ef634_59.png)

好第三种，第三种是什么呢，第三种是同样的，也是1000个县城，每个县城10万次递增，那么第三种呢我用的是lan adder。



![](img/c10a0ef9c5bb66130b1f7a78c18ef634_61.png)

![](img/c10a0ef9c5bb66130b1f7a78c18ef634_62.png)

对这个long adder呢count 3啊，第三种呢是long adder。

![](img/c10a0ef9c5bb66130b1f7a78c18ef634_64.png)

loadder呢在里面呢直接就是cm 3点increment，同样的1000个线程10万次递增好了，来我们来跑一下，看到最后的结果是一个对比，像这种小程序，你们自己呢应该要动手写一写，你才知道呢。

到底在哪种情况下效率会更高一些啊，哪种情况下的效率不高，哪种情况下会怎么样，好来看一个对比啊，这是一个一组数据，其中是有可能的一组数据，用atomic的时候呢。



![](img/c10a0ef9c5bb66130b1f7a78c18ef634_66.png)

它的时间是两秒三，然后think呢是三秒五。

![](img/c10a0ef9c5bb66130b1f7a78c18ef634_68.png)

along adder是一秒一秒二，所以从这可以看得出来，这个long long either呢是最高的，就是效率最快的，居高再来一遍，再跑一遍，你来讲吧，所以所有的东西都写一个程序里。



![](img/c10a0ef9c5bb66130b1f7a78c18ef634_70.png)

其实不太科学啊，不过呢嗯那至少能看出个大概来呃。

![](img/c10a0ef9c5bb66130b1f7a78c18ef634_72.png)

你会看到long adder啊，效率非常的高，不过如果你自己做实验的时候，你要是把线程数变小了，long adder未必有优势，你要是把那个循环的数量变少了，long adder也未必有优势。

所以你呢实际当中用哪种，你要呢自己呢要考虑一下，将来你的这种病发的这个并发的线程，到底有多少，并发率呢，到底有多高，这个高并发高并发啊到底有多高，如果说没有特别高的情况之下，你要是实际当中模拟啊。

你你会发现呢，未必a toma就是最好的，或者未必long editor最好的，那刚才我们分析过，为什么我们来说为什么，关键是你们我问你们一个问题，为什么atomic要比sk快效率高，为什么。

刚才我们说了不加锁，对不对，sironize，是要加锁的，有可能他要去，操作系统去申请这种重量级锁，所以simple net的效率偏低，在这种情形下效率偏低啊，一定一定要说清楚。

那long adder为什么要比atomic要高呢，其实long adder的内部是做了一个这种分段锁。



![](img/c10a0ef9c5bb66130b1f7a78c18ef634_74.png)

类似于分段锁的概念，你认真听我来简，给大家简单解释一下这个long为什么要比，其他的两个都要快，long either，由于呢我们这涨就是加的这个值呢，特别特别的高，所以呢在它内部的时候呢。

它会把这个值，放到一个数组里，你比如说最开始的时候大家伙都是零是吧，然后呢县城数特别多，咱们不是1000个县城嘛，那么其中呢，速度成为四吧，最开始是零，然后1000个线程吗。

他会250个线程锁在这个位置，250个线程锁在这个位置，250个锁，这个位置250个锁这个位置，然后每一个都往上递增，最后算出来结果之后呢，把所有的数加在一起，最后一加加一个总的。

几个数一加算一个总数啊，算了，所以long either在并发性特别高的情况下，尤其是线程数量特别多的时候，long adder就有优势了，如果说线程数特别少，其实long adder没什么优势好。

所以我们现在来看来分析一下，为什么synchroni，为什么atomic比synchronized高啊，很简单，因为他用了无锁的操作cs操作啊，为什么long ther要比tony还要效率还要高呢。

因为它内部用了这种孙调走，资料走概念非常简单是吧，嗯好那呃关于刚才的这个知识点，如果没什么问题啊，你老是扣一有问题直接提好吧，分段所里是ci操作，是的是的是的，分段所也是c a i操作啊。

这个你想一想也肯定是嘛，他面试有可能会问，说那个这个这个问道可能性不大啊，但是有可能我认为您应该掌握，本身这个知识点也不难，long accumulator，只要long either呢。

是long accumulator的一种特殊形式，long accumulator呢用的就更少了，不少同学已经搞不太清了是吧，dollar ada的这个这个情形下。

