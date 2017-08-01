# 1. 重装系统后Anaconda3环境变量的设置
* 右键此电脑-属性-高级系统设置-环境变量-Path-分别新建三个-
* C:\ProgramData\Anaconda3
* C:\ProgramData\Anaconda3\Library\bin
* C:\ProgramData\Anaconda3\Scripts

# 2.第三方库的安装
* 打开cmd 输入
'pip install wordcloud'
如果失败
* 下载whl whl放在C:\ProgramData\Anaconda3\Scripts文件下 shift+右键空白处
打开cmd 输入 'pip install 文件名.whl'

# 3.中文显示问题
* 简单方法
每次都进行设置
import matplotlib.pyplot as plt
plt.rcParams['font.sans-serif']=['SimHei'] #用来正常显示中文标签
plt.rcParams['axes.unicode_minus']=False #用来正常显示负号
有中文出现的情况，需要u'内容'

* 一劳永逸方法
import matplotlib
matplotlib.matplotlib_fname() #将会获得matplotlib包所在文件夹
然后进入C:\Anaconda64\Lib\site-packages\matplotlib\mpl-data该文件夹下就能看到matplotlibrc配置文件
1. 打开该配置文件，找到下面这行：
  #font.serif : Bitstream Vera Serif, New Century Schoolbook, Century Schoolbook L, Utopia, ITC Bookman, Bookman, Nimbus Roman No9 L, Times New Roman, Times, Palatino, Charter, serif
  然后，将前面的注释去掉！

2. 找中文字体放到matplotlib字体库中。

  在Windows文件夹下：C:\Windows\Fonts\Microsoft YaHei UI复制该字体，然后粘贴到C:\Anaconda64\Lib\site-packages\matplotlib\mpl-data\fonts\ttf文件夹，并给它重命名为Vera.ttf。

  注：我复制时出现了三个ttc文件选择其中一个改为Vera.ttf
