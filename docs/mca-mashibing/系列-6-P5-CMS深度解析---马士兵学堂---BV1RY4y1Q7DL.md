# 系列 6：P5：CMS深度解析 - 马士兵学堂 - BV1RY4y1Q7DL

好仔细听，我今天给大家讲cms是什么东西，这是面试的重灾区，这个c m s最重要的一个区域和和，和那个前面的最重要的一个区别是什么呢，前面叫做serial parala，这个叫什么呢。

这个叫concurrent concur，叫并发，并发的核心是什么东西呢，这个emostly concurrent，low pause，collector还是关键在这，low pause什么意思。

暂停时间特别短，t w的时间比较短，看这里cms关键就在这里，这张图你一看就能理解了，这张图是啥意思啊，就是我的垃圾回收线程跟我的工作线程，我们是同时在干活，这样我从外部访问来看。

由于我的工作线程在干活，所以你肯定能给我响应，与此同时，由于我的垃圾回收线程也在干活，空间会诶边玩边整理，边玩边整理，边玩边清理，听上去就爽多了好了，那么你可以想象一下，这是你家空间，这是你你女朋友。

你男朋友好，与此同时，这个时候会有谁呢，要是你爸爸你妈妈他们在干嘛，他们在帮你清理那些小线团啊，哎你们再产生一些小线团啊，哎他们在与此同时在清理吗，那这样的话大家很和谐，一派欣欣向荣的景象。

当然这是理想情况啊，1。8只支持g one吗，必须支持大哥好好，我来跟大家聊一聊呢，这个cms啊到底是它是怎么怎么来呃，能够做到这一点的，就是那个可以垃圾回收线程和工作线程，同时执行呃。

这里面会产生大量的问题啊，我可以告诉你啊，从cm开始往后，到g one到cdc和shindo啊，这里面的最重要的一个一个一个发展的历程呢，就是说怎么解决在并发过程中出现的一些问题，那我们来想象一下。

如果说我们一边产生对象，一边回收对象，同学们，你们想想一边产生一边回收，一边产生一边回收，会产生什么问题呢，会产生什么问题，最严重的问题是什么问题，最严重的问题就是本来你不是标记吗。

你把这哥们已经标记成垃圾了，但是在我后面运行的过程之中，很有可能又有新的引用指向他了，想想看，我又连上了好，我连上他了之后嗯，是什么情况，由于你已经标记完了，你已经把它标记为垃圾了。

你本来要把它给进行清理了，你下一步就要把它给清掉了，可以把它给干掉了，可是在运行过程之中，诶，你的你的女朋友又有啵扔，扔了一根线条，把它给连上了，她又不是垃圾了，那你这时候怎么办，就会产生错标。

这点上大家能想象的出来吗，来能想象出来的，给老师扣一嗯，嗯怎么会重新连上呢，怎么就不会呢，这是一堆的缓存，你得缓存，本来我在缓存里头命中这个了，命中了嗯，然后呢我用完了，然后还没来得及垃圾回收的时候。

本来他可以进行垃圾回收了，还没来及垃圾回收的时候，我下一个县城来了，又把它命中，这不就又连又连上了吗，这个很正常啊，就是我跑着跑着在里边玩嘛，玩着玩着就把这小线头本来扔了啊。

突然之间哎ok我就发现它有用，我就我就再把它连上了，所以这时候就会会产生错误，你懂吗，这是一个最核心的问题，是一个最根本的问题，就是会产生原来被我标记为垃圾的，后来又变成不是垃圾了。

在整个程序的运转期间，这哥们又不是垃圾了，所以我我是要亲它还是要不清的，我后面的清理过程，我是要清他还是不清的，好这个过程来，这个最最最麻烦的问题能够get到的，来给老师扣一。

嗯嗯当然还会有一些其他的那种小的问题啊，你比如说嗯刚才是是是是轻微垃圾的，编程不是垃圾了，还有一种呢是呃不是垃圾的，又变成是又变成是垃圾了，本来你标记的过程之中，这哥们不是垃圾，可是随着程序的运转。

这哥们儿又变成垃圾了，像这种的这种倒是无所谓，这种你下一次在清理过程之中，你就把它找出来了，所以这种叫浮动垃圾，叫floating garbage，但这个有点细了啊，我们先把这么细的东西先放一边。

我们先来理解一下，这个cm s是怎么解决这个问题的，cm是怎么解决这个问题的，仔细听，你your girlfriend，your boyfriend cms是这么干的，它会进行一个初始标记。

上来之后我要清理了，暂停依然是s w，有同学说老师他还是有s t w啊，对依然有各位同学，到目前为止，所有java的垃圾回收器都存在s t w，所以下次不要再问我这个问题了，所以有没有s t6 。

听我说，我再说一遍，所有java的拦截回收器都有sw，所有go语言的拦截回收器都有sw，python也有，只有某种语言的没有，你们猜猜是哪种语言，c那不废话吗，c是自己管理的，我说有垃圾回收器的。

还没有s t w的，就是你不用不是垃圾回收器，就是你不用自己管理那垃圾，然后还没有s t w的，有没有唉，只有一种rust，目前只有一处，ruby no donut，no，rust是啥。

rust是一种馒头的牌子，嗯以后要多吃啊，rust听上去就好吃，你想一个一个一锅大白馒头蒸出来哇，冒着热气啊，甜甜的感觉，rust，rus为什么这么牛，后面讲给你们听，rose的牛呢。

它的原因在于编译它的编译器做的特别牛，它采用了租界的概念，好了不说了，这个扯的有点远了啊，再说，所以c m s的第一步呢是叫做初始标记，这个初始标记干一件什么事呢，他就是找到那些根对象，听懂了吗。

因此它确实有s t w，但是他时间不会太长，为啥呢，因为你的根最小没那么多，跟对象很少的，这是你的根对象，然后根下面啊管理的一系列的list，一list里面有管理，有要练练练上一系列的对象啊。

这个对象里面有一些成员变量等等，这个里面还是大量的找到根对象并不难，因此这个s t w时间并不长，他是可以接受的，几十个毫秒啊，几百个毫秒而已，好最复杂的，最容易产生产生最耗时间的。

其实是跟对象下面找这颗对象树，去滤过滤这边这个这个对象数哦，但是正好在过滤对象数这里会产生它是并发的，就是我的垃圾回收线程一边过滤这个对象数，你的工作线程也可以改变这颗对象树嗯，那么大家你想一下。

就会产生我刚才所说的漏标问题，就是本来这哥们儿不是垃圾，结果你把它给清了，这肯定不行，那怎么纠正这个问题呢，纠正这个问题，c m s采取的标记，这个这个做法是这样的，他下一步再采取一次s t w。

在在重新标记这个阶段里头，听我说cms的区别，jy的区别，z gc的区别，他们重要的区别就在这儿，c m s叫做cms和g one和go语言，采用的都是三色标记，而z dc采用的是颜色指针。

叫color pointers，我们先说结论吧，好吧我我我这个是不是是不是能能说清楚啊，你说的对啊，你说的特别对啊，我错了，thank you，我再说一遍啊，再说一遍，不知道就这点呢是你面试的时候。

能不能跟面试官聊清楚的，关键点，就是你跟面试官聊清楚这个问题之后，我跟你说，基本上是那那基本基本这个岗位已经拿下了，好吧，再说一遍，由于我的病发，我的垃圾回收器跟我的那个工作线程同时进行。

会产生一种什么情况，都会产生一种错标，鼠标的意思是什么，原来这哥们已经被你标记为垃圾了，但是运行过程中它又变成不是垃圾了，但是你一定要保证不能把它给回收掉，那这个机制是怎么做到的。

目前采用的有好多种算法呃，cms和g one他们采用的都叫做三色标记，只不过呢采用这个三次标记，c m s呢它的细节呢叫incremental update，叫增量t增量更新。

而g one呢叫s t b叫natural at the beginning，叫快照，然后cdc采用的是什么，cdc采用的颜色指针，颜色指针，它是采用了操作系统里面的虚拟空间的概念啊，颜色指针对好。

大家先记着这个结论就行了好吧，就是第一遍先先找根儿嗯，中间的过程呃，不断的进行标记，标记标记，然后最后再来一个重新给它，把错标的部分再给它纠正过来，纠正完了之后呢，再进行清理。

那有同学在这可能也会问说老师，你在清理的过程中也是并发的，那这个时候又产生了新的垃圾呢，产生新的垃圾，下一次一个循环再给他弄过来了，所以这种垃圾就叫做浮动垃圾，就是在你垃圾清理的过程之中产生了新的垃圾。

floating damage，好，这个大体的过程除了中间的三色标记算法之外，我再说一遍，整个大体的过程，除了中间的三色标记算法之外，来能get到的，给老师扣一，嗯嗯让我们来那个稍微的复习一下啊。

cm的初始标记的时候只是找到根对象，ok cm s找到根对象之后会并发进行标记，在标记的过程之中啊，注意看啊，找个对象品牌标记，标记过程中，很可能这个地儿啊，你原来已经被你认为是垃圾了。

可是很不幸在运行的过程中，它又变成不是垃圾，由于引用指向它了，好它又变成不是垃圾了，那这时候怎么办呢，会进行一个remark，remark又把它标志变成不是垃圾，然后剩下那个那才是垃圾，把他清掉好了。

你后面要讲算法，想想看是不是有点有点懒累，我们讲实战吧，算法扔一边可以吗，讲实战吧啊嗯讲算法也是要花大量的时间，而且他嗯，这东西你可以在面试之前背一遍就行了啊，三色啊，那个以后嗯我们我们还是聊实战好吧。

来聊想听算法的扣一，想听实战的，想想想想听实战的扣一啊，sorry想听实战的扣一，小宁算法的扣，7695x6443等，最后的结果，呃呃呃呃呃嗯嗯哈哈哈哈，看来还是还是喜欢听那个那个那个实战的，居多是吧。

算法太难了，对嗯你先记着三色流线就300，这东西你弄弄明白一遍就可以，但是我要给你扣算法的话，那没有个一个半小时，我跟你说扣扣扣不出来的，哎这里面细节太多了，就cms的解决方案和那个jy的解决方。

算法就背哈哈哈，也不能是背了，呃其实你理解的算法越多，你个人的水平就越高，然后你你能够产生你的那个那个那个，你你你你你自己的这种思路呢，也就慢慢的建立起来了啊，真的要停算法是吗，好那我正式问一遍啊。

想听算法扣一，想听实战扣二，我看哪个多哪个少啊，那今天给大家讲算法，明天给大家讲实战可以吗，嗯都都都招不到。

