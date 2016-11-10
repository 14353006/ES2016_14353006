##DOL实例分析&编程##
###任务###
1. 修改example2，让3个square模块变成2个。
2. 修改example1，使其输出3次方数。
###操作步骤###
1. **修改example2，让3个square模块变成2个。**
	- 打开example2中的example2.xml文件
	- 如图，可以看到此处square的循环次数，value值为3

		![picture1](http://a4.qpic.cn/psb?/V11wIoXg0U0Il1/0bpHdNYyEOuk6dATK0sn9Oq6TGSCo4Ai2NfD9wbxOeE!/m/dHcBAAAAAAAAnull&bo=GgEXAAAAAAADBy4!&rf=photolist&t=5)
	- 修改此处代码，将value改为2
		
		![picture2](http://a3.qpic.cn/psb?/V11wIoXg0U0Il1/i6E4rVVVVG848nldoMTR1eYutWVlkZMrYCjrFAXqH7c!/b/dAoBAAAAAAAA&bo=MAEWAAAAAAADBwU!&rf=viewer_4)
	- 重新编译和运行，得到新结果，结果由三次平方变为两次平方
	
		![picture3](http://a1.qpic.cn/psb?/V11wIoXg0U0Il1/zmxG1DYQRPrMIjVlVXUVfgNqPKIibVurIUPMACBfW9g!/m/dAwBAAAAAAAAnull&bo=pAGxAQAAAAADBzc!&rf=photolist&t=5)
	- 其dot图如下
		
		![picture4](http://a1.qpic.cn/psb?/V11wIoXg0U0Il1/pOrqDHDKkS6IyxHJx10Kxmmvk*FjSZ0wg8WVLGi4VPU!/b/dHcBAAAAAAAA&bo=3wI.AgAAAAADAMQ!&rf=viewer_4)
	
2. **修改example1，使其输出3次方数。**
	- 打开example1中的square.c文件
	- 如图，可以看到此处实现square的具体代码："i=i * i"

		![picture1](http://a2.qpic.cn/psb?/V11wIoXg0U0Il1/jJ3szl71cZNoUKpDZIpTaTtxmngbr9glCmqiMGbSiUI!/b/dAkBAAAAAAAA&bo=4wFdAAAAAAADAJo!&rf=viewer_4)
	- 修改此处代码，将其变为立方，即 "i=i * i * i"
		
		![picture2](http://a2.qpic.cn/psb?/V11wIoXg0U0Il1/Dt0IQXkVc*tAWSoV8lx5swYeLz*mBgNJCs9h1uCB3BA!/b/dNwAAAAAAAAA&bo=4wFxAAAAAAADB7E!&rf=viewer_4)
	- 重新编译和运行，得到新结果，结果由二次方变为了三次方
	
		![picture3](http://a3.qpic.cn/psb?/V11wIoXg0U0Il1/ScDWjsW*iqnO.zBFgkPcJMQx0MMm4U6FQykAP.5eYCU!/m/dAoBAAAAAAAAnull&bo=pAHPAQAAAAADB0k!&rf=photolist&t=5)
	- 其dot图如下
		
		![picture4](http://a1.qpic.cn/psb?/V11wIoXg0U0Il1/9kYz3TYBZ3C1CpqueLCFRq7Rj6E2gC1A7FZ3*L4GdWo!/m/dNwAAAAAAAAAnull&bo=3AI6AgAAAAADB8Q!&rf=photolist&t=5)
###实验感想###
此次实验比较简单，各个部分都比较好理解，需要改动的地方也不是很多，其中值得一提的是在每一次修改了文件之后我们都需要重新编译一次，然而编译时build/bin/main中的example是不会被替换掉的，所以我们需要删除原本的example，再次编译后重新生成新的。另外dot图相当之直观地表现出了这个程序的流程，便于我们理解。最后想说的是，原本我认为markdown是一个相当方便的工具，甚至可以考虑一下替代word，但是这次之后发现还是有些麻烦的地方的，比如说图较多时重复传图取地址十分麻烦，另外就是关于文字内若有*、#等特殊符号时会影响排版，我目前还没有找到太好的解决方式，只能通过空格稍微区分一下。




