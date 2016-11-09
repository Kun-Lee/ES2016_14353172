#DOL实例分析&编程
----------------------
##example中各文件的含义：
-----------------------------
<pre>
src文件夹：各进程（生产者，消费者，处理模块等）的功能定义；文件夹内包含.c和.h两种  
文件，就是实现的模块，即*.dol的框架的功能描述；  
.xml文件：系统架构即模块连接方式定义；定义模块与模块之间的连接方式；其中proces是  
框架，sw_channal是线，connection就是连线的脉络。
</pre>
----------------------------------------------------------------------------------------------------
##exmaple1分析：
![#.dot1](http://a3.qpic.cn/psb?/V10xhQuy3m7suY/gpmj8eJPIkGQSUQi8PMkCdxLCMAHGKppBzFdI7pB8Tk!/b/dHwBAAAAAAAA&bo=.gHiAAAAAAADBzs!&rf=viewer_4)  
如图；生产者和消费者只是发送和接受信号，其中的处理过程在square中做；所以example1只需要在square中处理即可；
![example1](http://a2.qpic.cn/psb?/V10xhQuy3m7suY/LaJEn77w3QGODJ5GZNTvZARwp7tEj956CTvLmuzSlWc!/b/dNwAAAAAAAAA&bo=iANQAgAAAAADAPw!&rf=viewer_4)  
一开始example1的迭代次数为2，square中改动迭代次数即可；
##example2分析：
![#.dot2](http://a2.qpic.cn/psb?/V10xhQuy3m7suY/rL*2PQTXAnVhdWh7fkIfEVXdncM9g9eZC.lsIQIvKc4!/b/dNwAAAAAAAAA&bo=SQTCAAAAAAADB60!&rf=viewer_4)  
进程定义与example1很类似，只是这里有3个square；因此处理的思路也很清晰，只需要在.xml文件将迭代次数N减1即可；  
如图：  
![example2](http://a3.qpic.cn/psb?/V10xhQuy3m7suY/ri*4jzrePox6gdlZ5u*9hiFy3s0U39kHHqZYIkE2UtM!/b/dAoBAAAAAAAA&bo=hANQAgAAAAADAPA!&rf=viewer_4)  
可以看到N==2，即迭代次数为2；i^4不为i^8;  

--------------------------------------------------------------
##example运行结果：
----------------------
### 在虚拟机中打开**terminal**，输入指令:  
<pre><code>
$	cd dol
$	cd build/bin/main
$	ant -f runexample.xml -Dnumber=1
$	ant -f runexample.xml -Dnumber=2
</code></pre>
**在每次改动example之后要删除build并重新编译一次build.zip.xml**

-------------------------------------------------------------------------
##得到最终结果
**example1结果图**
![example1结果图](http://a1.qpic.cn/psb?/V10xhQuy3m7suY/RyJHZnDKDGj08GvPRZu9bh*QqKCdNratuqBN6KQwiv4!/b/dHcBAAAAAAAA&bo=nQJXAgAAAAADAO8!&rf=viewer_4)    
---------------------------------------------------------------------------------------------
**example2结果图**
![example2结果图](http://a3.qpic.cn/psb?/V10xhQuy3m7suY/aAk3UU.jPOs99SvxhNA1eljFGnlRmaBy69hpFMWug6A!/b/dNoAAAAAAAAA&bo=oQJWAgAAAAADANI!&rf=viewer_4)  
**example2 dot图**
![dot](http://a3.qpic.cn/psb?/V10xhQuy3m7suY/NUrT61NVYa*U8Tly4cq*yAv41IrftoMBQfCtFRAuIXw!/b/dAoBAAAAAAAA&bo=1QJxAAAAAAADB4Q!&rf=viewer_4)  
##实验感想  
-------------  

这次实验本质上不是很难，在嵌入式的框架上也是老师讲过的，实验的处理方法和终端的运行TA上课和课件也有很详细的说明，难度不大；但对于dol的编程有了更深的理解。  

----------------------------------------------------------------------------------------------------








