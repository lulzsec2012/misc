#Anaconda使用手册
##1. 基本知识
	Anaconda默认是干净的，而且无法直接使用系统已安装各种库。例如：Anaconda默认不带opencv包，而且无法直接使用系统已安装的opencv，需要用户在 Anaconda下再次安装，命令如下：(如果出错可以多重复几次)
`conda install --channel https://conda.anaconda.org/menpo opencv3` 或者直接 `conda install opencv3`

	除了python外，Anaconda还默认安装了下面几个工具：
	* Anaconda Navigtor：用于管理工具包和环境的图形用户界面，后续涉及的众多管理命令也可以在 Navigator 中手工实现。
	* Jupyter notebook ：基于web的交互式计算环境，可以编辑易于人们阅读的文档，用于展示数据分析的过程。
	* qtconsole ：一个可执行 IPython 的仿终端图形界面程序，相比 Python Shell 界面，qtconsole 可以直接显示代码生成的图形，实现多行代码输入执行，以及内置许多有用的功能和函数。
	* spyder ：全称为the Scientific PYthon Development EnviRonment，一个使用Python语言、跨平台的、科学运算集成开发环境，是一个免费的交互式开发环境。在anaconda安装完成之后，直接在终端输入spyder命令即可启动。 

## 2. 安装Anaconda
	* 下载anaconda，网址为：https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/。该镜像站中包括了大部分anaconda的版本，在这里，我用的是“Anaconda2-2.4.1-Linux-x86_64.sh”，希望大家统一一下使用这个。
	以“Anaconda2-2.4.1-Linux-x86_64.sh”为例，解释一下文件名的意义：Anaconda2说明是基于Python2的版本，2.4.1是具体的版本号，Linux是指适用于linux系统，x86_64表明适用于64位系统（如果只有x86.sh，表明适用于32位系统）。

##3. 使用conda
	一般流程是：先新建环境（见3.1的第2条），再激活环境（见3.1的第3条），配置并安装需要的包（遵循3.2），退出环境（见3.1的第3条）。

###3.1 基本使用
	1）删除anaconda：由于anaconda在linux下是安装在一个文件夹里/root/anaconda ,如果安装过程中出错问题，或者想更新另一个版本，删除anaconda也很方便，执行下面命令 
	rm -rf ~/anaconda

	2）建立一个 conda 环境，conda create -n <env_name>  python=2.7。
	例1：conda create -n ydwu-tmp python=2.7
	# 新建一个名为ydwu-tmp的环境，并指定python版本为2.7，若不指定python版本则使用系统默认python版本。
	例2：conda create -n <env_name> numpy matplotlib python=2.7:
	# 新建env_name的同时安装必要的包.并不需要在新建环境时就安装包,一般都可以在新建环境之后再做。

	3）激活/关闭环境，即打开/关闭一个环境（linux系统）：
	激活环境：source activate <env_name>
	关闭环境：source deactivate <env_name>
	若是Windows系统，则activate <env_name> 和 deactivate <env_name>。

	4）查看当前系统下的所有环境。
	conda info -e

	5）移除指定环境
	conda remove -n <env_name> --all

	6）复制一个环境
	conda create -n <env_name1> --clone <env_name2>	

	7）导出环境到文件
    conda env export > environment.yaml

	8）从文件导入环境
	conda env create -f environment.yaml

	9）查看anaconda的版本
	conda --v
			
	10）通过conda -h或conda –-help，可以查看更多指令。

	11）通过conda -h或conda –-help，可以查看更多指令。

	注意：在以下的使用过程中你会发现使用conda下载包的速度非常的慢，因为使用的是国外的服务器，所以这里要设置为国内的镜像。使用下面的配置命令即可：
	//添加Anaconda的TUNA镜像
	conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
	//TUNA的help中镜像地址加有引号，需要去掉
	//设置搜索时显示通道地址
	conda config --set show_channel_urls yes
###3.2 包管理(即环境配置)
	1）查看安装时自带的Python扩展包（package）：conda list
	查看指定某环境下安装的包：conda list -n <env_name>

	2）查看可用软件包：conda search

	3）安装软件包。给某个特定环境安装包有两种方式：
	一是切换到该环境下直接安装，如“source activate <env_name> && conda install <package-name>”。
	二是安装时指定环境参数-n，如“conda install -n <env_name>  <package-name>”。
	如果需要指定包的版本，需要使用 [package-name]=x.x。
	(如果要在所有环境中安装包，“conda install anaconda”或者“pip”。??????)

	4）更新包
	conda update <package-name>			
	
	5）卸载包
	conda remove <package-name>

##参考
	http://python.jobbole.com/86236/
