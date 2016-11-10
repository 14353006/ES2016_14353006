##DOL开发环境配置##
###Description###
分布式操作层（DOL）是一个用于编程并行应用程序的软件开发框架，其允许特定的基于卡恩过程网络计算模型的应用程序，并提供基于SystemC的仿真引擎。此外DOL提供了一个基于XML的特定格式来描述在多处理器系统上并行应用程序的实施，包括绑定和映射。


![picture1](http://a1.qpic.cn/psb?/V11wIoXg0U0Il1/ln5oxKl49r6xsVCO1cLtFsJY4PFWZxtuR5Q1TtG4*qE!/m/dAQBAAAAAAAAnull&bo=8QMqAvEDKgIDCC0!&rf=photolist&t=5)

###How to install###
1. **为ubuntu安装一些必要的环境**
	- $	sudo apt-get update
	- $ sudo apt-get install ant
	- $ sudo apt-get install openjdk-7-jdk
	- $ sudo apt-get install unzip 
2. **下载dol文件和systemc文件并解压**
	- 新建dol的文件夹
		- $ mkdir.dol
	- 将dolethz.zip解压到dol文件夹中
		- $ unzip dol_ethz.zip -d dol
	- 解压systemc
		- $ tar -zxvf systemc-2.3.1.tgz
3. **编译systemc**
	- 解压后进入systemc-2.3.1的目录下
		- $	cd systemc-2.3.1
	- 新建一个临时文件夹objdir
		- $	mkdir objdir
	- 进入该文件夹objdir
		- $	cd objdir
	- 运行configure(能根据系统的环境设置一下参数，用于编译)
		- $	../configure CXX=g++ --disable-async-updates
	- 编译
		- $	sudo make install
	- 记录当前的工作路径
		- $ pwd
4. **编译dol**
	- 进入刚刚dol的文件夹
		- $	cd ../dol
	- 修改build_zip.xml文件
		- 找到下面这段话，就是说上面编译的systemc位置在哪里，
		- property name="systemc.inc" value="YYY/include"    
		- property name="systemc.lib" value="YYY/lib-linux/libsystemc.a"
		- 把YYY改成上页pwd的结果
	- 编译
		- $	ant -f build_zip.xml all
		- 若成功会显示build successful
	- 运行第一个例子
		- 进入build/bin/mian路径下
			- $	cd build/bin/main
		- 然后运行第一个例子
			- $	ant -f runexample.xml -Dnumber=1
		- 若成功会显示build successful,如下图：
		
			![picture2](http://a4.qpic.cn/psb?/V11wIoXg0U0Il1/AGMEfRqvNn53NzUhGOmRAur1EHNeelzCgV*PnYDAEQA!/m/dHcBAAAAAAAAnull&bo=fAJhAgAAAAAFBzk!&rf=photolist&t=5)
###Experimental experience###
本次实验对我而言相当的有趣，接触了Git和Markdown两种工具，其功能和体验都是我之前没有尝试过的，我确实地感受到了使用一个好的工具会带来的高效。在大概地看了一下Git教程后，觉得它解决了之前一直很困扰我的一个问题，就是修改代码时需要不断的保存先前修改至一半的代码导致最后自己也搞不清楚，我觉得在接触了Git并足够熟悉之后我会尝试着将其强大的功能融入我的代码生涯中。另一方面Markdown真的是一个令我叹为观止的工具，正如我目前在编辑这个文档时感受到的，相比word的格式，使用Markdown调整相当轻便，易于排版，以后的实验报告简直都想要用Markdown做，但是关于导入图片这一块一开始我是不大懂的，后来看教程发现了上传图片需要的“图床”，稍微尝试了一下也就解决了这个问题。