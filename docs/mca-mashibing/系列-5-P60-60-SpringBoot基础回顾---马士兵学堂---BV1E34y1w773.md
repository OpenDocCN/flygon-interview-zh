# 系列 5：P60：60、SpringBoot基础回顾 - 马士兵学堂 - BV1E34y1w773

![](img/8e4bcff154b61d130311a2c81ac90181_0.png)

此时源码黄师傅讲过了，如果你们觉得还是听得不太特别清楚的话，到时候我在基础班的时候要不要重新讲一遍，重新讲一遍这东西好了，今天呢我们接下来讲我们spring boot，相关的一些知识点。

然后上节课讲完之后呢，我们讲的都是些基础的配置和应用层面的东西，很多学生说老师那个我刚学这东西，然后呢可能学的不是特别清楚，你能不能帮我写一份笔记，所以这边呢给大家准备了一些笔记，给大家放在这个地方了。

我在看到有很多markdown文档，好吧，很多东西都已经写好了，所以一会儿下课之后，我会把这个笔记给大家分享出来，以后看笔记就够了，OK我们先来对上节课的一个知识，做一个回顾好吧。

而MYSQL基础家调小课啥时候出呃，正在剪，正在剪那个视频要剪辑啊，咱们那个视频网站，大概在1月1号的时候会上线啊，一号会上线，你会看到就是一个全新的一个视频网站啊，现在还没做好，现在还没做完。

还差两天时间，做完之后，你们从从那个视频网站上就能看对应小课了，好吧好了，我们先来回顾一下上节课大概讲点什么东西，其实讲东西啊也比较简单好吧，就是spring的一个spring boot的一个基本入门。

然后加上一些相关的一个配置配置文件，这一块，很多同学啊可能之前没学过那个SSM哦，SM所以导致说老师这个spring spring boot配置啊，我不太清楚不太清楚也没关系。

这边呢给大家整理了一个文档，好给大家整理一个文档，文档里面讲的就是spring boot配置相关的东西，就是我们配置的时候，在之前的时候可能大家更青睐于用XML文档好，XMLXML文件在进行配置的时候。

每一个框架还有自己配置文件的格式，而现在到spring boot之后，你只需要配置到我们单独的spring boot的配置文件里，就可以了，那个配置文件，它支持第一个properties这样一个形式。

好，properties这样一个文件格式就是K，然后写一个等于V这样的格式，第二个可以支持什么叫YAM2好，YM或者说YML都行好吧，这是这样的一个配置文件，然后这边给大家想写了一些比较详细的配置。

比如说如果我要用properties的话，我应该怎么做配置，OK然后呢创建实例对象应该怎么进行一个引入，引入的时候也是一样，可以通过我们的ADD value来进行引入，这比较基础了或者比较简单好吧。

之前你们在学spring的时候，大家都都都是这么配的，SPMC的时候都是这么配的好吧，第二个，这有一些测试类的一个测试，下面还说了，除此之外，在我们的propose文件里面。

还可以引用相关的一些随机数的一些类，这东西啊，上节课我是没讲的好吧，这东西到哪哪来的，也是从官网里面直接拿过来的，东西还是一样，不废话，我直接带你们看官方网站里面包含的东西，这是英文的，是中文的。

给大家找到中文网站网站，你们从中文上直接看就行了啊，很多同学说老师我找不到这个中文网站，我给大家发一下，我给大家发一下，你把这东西好好看看好吧，里面有一块是专门针对我们的YM2的，我找一下，这太多了啊。

看这块他说了，使用亚马来代替我们这样的一个文件属性，里面告诉你说他是一个什么叫K，然后呢冒号V它是一个分格式的一个形式，写的下面有各种各样转换的一个形式，比如说多profile ymar的一个文档。

然后呢后面还包含我们对应一些缺点，然后按全属性的一个配置，以及后面说可以使用一些随机变量，找一下刚写代码就从官网里面粘的松三绑定，这就没有了，随机数呢，哎我的随机数呢没有了，没有了吗，找不到了。

你下去自己找一下吧，反正就是在关关于我们这个随机数，这有一个配置，这个配置哪去了，反正就是从官网里面粘出来的那个代码，都是从官网里面一模一样的代码，然后呢我只能帮你在项目里面写了一下。

然后把配置文件给追上了，大家看到了可以怎么写呢，用dollar符号加一个大括号，写个random value，Random int random lag，它分别会转换成对应的一个随机数的一个值。

也就是说之前我们写随机数的时候，必须要在java代码里面写一个random的一类，然后呢next什么东西现在不需要了，这直接能帮我们进行生成，然后后面也一样。

可以通过at value这样的一个标签进行一个引入，引入，这代码我不带你们写了非常基础的东西，下载之后粘到你的IDE工具里面，直接运行就可以了，这个文档写的比较全好吧，第三个就是多环境的一个配置。

这不用说了吧，比如说我们可以通过spring profile active好吧，通过这样的一个属性值，然后指向我们的DEV或者text，或者说大PROD，就生产环境可以由多环境进行一个切换。

这块东西啊也一样，下去之后自己去测，OK这上节课讲的东西啊，我们检测一个回顾，下面我说了，除了用properties之外，还可以用一个东西叫YMYM好吧，他什么东西啊。

他说不是一种标记语言的一个外语缩写，但是为了强调这种语言以数据作为中心，而不是以标记语言作为中心，而用反谱词重新命名，反正这东西啊很奇葩很奇怪，你知道它只是配置文件的一个形式就行了，现在回顾没关系。

现在回顾上节课都说过了好吧，然后告诉你说他是一个什么样的形式，比说了语法比XML简单很多，然后告诉你它有一些语法的规则，注意下就行了，然后如何进行编写啊，这里边写了，如果你要完成一个多环境的话。

可以用spring，然后property，然后呢active加上它后面会用杠杠杠做一个分割，这表示DV的环境，这表示test环境这块，你可以选择，你到底使用哪个环境的一个具体配置。

也就是说我们现在之前上去给大家演示的时候，我写了多个EML文档，YAYAM2文档，现在呢你可以把它写到一个里面去了，但是要加三个杠，把它做一个基本的分割，好看的更舒服一点，这是第一点，第二点。

它也可以支持我们这些属性值的一个赋值，而且你在使用这个文档进行赋值之后，它在其他属性之方也依然可以引用，我们上面指定好的变量值，又写了一个dollar person name。

Major personage，是不是可以接引用了，然后在我们实体类里面想注入这些值的话，可以怎么注入，叫configuration properties，前面必须要加一个前缀。

因为这块它是一个是一个缩进方式来表示的，person表示说，我可以引入里面对应的一个属性值了，然后引入的时候它就会自动进行装配，就不用管它，但是而且呢它只是一个松散绑定，就算你的名称写的不是那么一样。

它也能绑定上来，但是不要区别太大，因为松散绑定它有自己的一套语法标识，好吧，刚刚在官网里面看了吧，这个是不是有它的一个缺点，别这样哦，松开绑定，好兄弟们，怎么回事，这给你演示出来了，好吧。

告诉你说呃什么风格，然后建议在什么什么东西使用，然后建议什么图形标识，下划线表示法，大写风格等等东西，这块从官网里面能看到很多的一个信息，这块只给大家做了一个总结文档。

然后再往下做了一个configuration，properties和value的一个对比好，他们两个有什么样的一个特点，OK所以这个文档我代码都给它粘出来了，你下去之后拿这个文档好好配一下就行了。

这东西没啥可说的，如果很多同学是刚接触的话，熟练一下，如果是接触的比较久了，在公司里已经使用了这块，直接跳跳过去，不用看了，好吧行了，那关于我们spring boot它的基本配置。



![](img/8e4bcff154b61d130311a2c81ac90181_2.png)