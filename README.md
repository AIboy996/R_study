# R_study
学习R语言的个人随笔

## 参考资料
主要是跟着《R语言实战》(R in Action, Robert I.Kabacoff)这本书来学习；
也会在google上找一些疑惑点记录下来。

## 文件内容
1、按照学习的进度，每一天一个文件夹，里面包含jupyter的笔记、生成的文件、R的工作空间；
2、上述参考资料的随书源代码《RiA_Source_Code》；
3、如何配置jupyter来同时在jupyter上使用R语言内核和python内核。

### 上述的3、，具体如何实现
首先声明，本方法是基于anaconda安装的jupyter；
1、确保你的jupyter notebook正常工作
2、去官方安装R语言，以及Rstudio（非必要，但是推荐）
3、在Rstudio的console中键入命令
```
install.packages(c('repr', 'IRkernel', 'IRdisplay'), repos= c('http://irkernel.github.io/', getOption('repos')))
```
安装必要的包
4、进入anaconda的安装目录，然后进入jupyter的内核目录；
（我的为D:\Anaconda\share\jupyter\kernels）
5、在kernels文件夹内应该有python3这一文件夹，复制粘贴一个副本，命名为R
6、进入刚刚复制的R文件夹，修改kernel.json
修改为
```
{
 "argv": [
  "E:/R-4.0.3/bin/x64/R.exe",
  "--slave",
  "-e",
  "IRkernel::main()",
  "--args",
  "{connection_file}"
 ],
 "display_name": "R_x64",
 "language": "R"
}
```
注意R.exe的路径

6、logo文件可以自行替换，或者直接删掉，亦或是不动。
