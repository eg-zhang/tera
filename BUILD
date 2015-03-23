
如何构建Tera？

*****************************************************************

Tera的构建是很简单的。目前，有两种方式供你选择，区别在于编译依赖
的管理：如果你希望自行管理Tera的依赖软件，请选择方式A，如果你想轻
松一点，请选择方式B。

*****************************************************************
**                         构建方式A                           **
*****************************************************************

首先，确认你的系统上已经安装了以下Tera的依赖软件：
* protobuf
* snappy
* sofa-pbrpc
* zookeeper
* glog
* gflags
* gperftools或tcmalloc
如果没有，先安装它们。最方便的方法是使用你的系统上的软件包管理器，
例如apt-get、yum等等；或者通过源码编译。源码的下载地址可以参考
build.sh。

当你已经安装好上述所有软件，请使用编辑器打开depends.mk，你会发现
depends.mk里面有三类变量，*_INCDIR是软件的头文件目录，*_LIBDIR是
软件的连接库目录，而*_PREFIX是软件的安装目录，一般来说头文件目录
和连接库目录就位于安装目录之下。如果软件是通过软件包管理器安装的，
它会被安装在系统的默认安装目录下，如/usr或/usr/local；如果是通过
编译源码安装的，并且没有加上--prefix参数，它同样会被安装在默认目
录下；如果指定了--prefix，那么这个参数就是安装目录。请把各个软件
的安装目录填写在相应的*_PREFIX=之后。*_INCDIR和*_LIBDIR仅在软件
的头文件和连接库不在一起时才需要修改。

编辑完depends.mk之后，保存它，执行下面三个命令：
  sh build_version.sh
  make proto
  make -j4
如果三个命令全部执行成功了，那么恭喜你，tera构建完成了。否则的话，
请检查依赖软件的版本，是否和建议的版本不同，过旧或过新的版本都有
可能导致编译失败。

*****************************************************************
**                         构建方式B                           **
*****************************************************************

使用这种方式，你将无需关心编译依赖，但是只能在接入互联网的情况下
进行。执行下面这个命令：
  sh build.sh
经过漫长的等待，tera就构建完成了。
但是你仍有可能失败。一些软件的下载地址可能已经失效（可能性很低，
我们会经常检查的）；一些软件的下载地址你也许无法连通，可以换个网
络环境试试，或是使用代理服务器。


