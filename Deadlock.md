##Deadlock##
###死锁的产生过程及结果###
- 完成Deadlock.java文件，如下图
	
	![D.java](http://a1.qpic.cn/psb?/V11wIoXg0U0Il1/PWGMd4rBspZjBwlbH6BOaB1ohtMiHZiVmFfsu4xNgUk!/m/dHwBAAAAAAAAnull&bo=VQKLAwAAAAADB*0!&rf=photolist&t=5)
- 在命令行中执行指令javac Deadlock.java，以获得Deadlock.class文件		
- 完成Deadlock.bat文件，如下图，将该文件置于Deadlock.class目录下
	
	![D.bat](http://a1.qpic.cn/psb?/V11wIoXg0U0Il1/FQTjFaXK*ntl6myi6L05Ukr9tl2OvFyD2WEQCEgElVY!/m/dAwBAAAAAAAAnull&bo=bAEdAQAAAAADB1M!&rf=photolist&t=5)
- 双击运行批处理文件，获得结果如下图
	
	![Deadlock](http://a1.qpic.cn/psb?/V11wIoXg0U0Il1/Qaz7L4kujUS5lR1Ew2GvwaauEHJrZ*L2y5PJu*VUPRg!/m/dHwBAAAAAAAAnull&bo=TQMpAgAAAAADB0c!&rf=photolist&t=5)
###产生死锁的4个必要条件###
1. **互斥条件**：一个资源每次只能被一个进程使用
2. **请求与保持条件**：一个进程因请求资源而阻塞时，对已获得的资源保持不放
3. **不剥夺条件**：进程已获得的资源，在末使用完之前，不能强行剥夺
4. **循环等待条件**：若干进程之间形成一种头尾相接的循环等待资源关系
###对产生死锁的解释###
首先从Deadlock.java文件来看，我们首先定义了类A和B，其中包含两个方法method和last，关键点在于方法之前的修饰：synchronized。当一个线程访问object的一个synchronized同步代码块或同步方法时，其他线程对object中所有其它synchronized同步代码块或同步方法的访问将被阻塞，也就是说这两个方法之间是**互斥**的。正常情况下该文件在主函数启用了线程t，等待一段时间（由count控制）后会运行run（）中代码，即b.methodB(a)，在这段等待的时间内主函数中已经完成了之后的a.methodA(b)，但是在之后的批处理文件中我们循环不断地运行Deadlock.java文件，使得在运行b.methodB(a)时，进程又运行a.methodA(b)，此时二者同时控制着自己的method()又需要调用对方的last(),便构成了**循环等待的条件**。又由于其请求和保持条件、不剥夺条件最后便造成了这个死锁。