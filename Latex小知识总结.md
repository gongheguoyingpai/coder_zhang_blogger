一般发表论的话都需要使用Latex进行排版，而在排版时难免会遇到一些不太常用的
效果，因此，结合本人的写作经验，总结一下小的Latex排版的技巧和资源。

一般Latex排版用的比较多的应该是Ctex吧！至少我身边的很多人都是在用这个。

1.扩展包的下载问题
这样的话就首先涉及到第一个问题了，如果用到Ctex里面不存在的包怎么办？我自己使用
的时候发现如果以Latex形式编译的话，如果用到不存在的包其会自行下载，但是如果直接编译为pdf的话，则需要自己去安装一些扩展包，这里主要是给出一个包的下载地址:[latex扩展包下载地址](http://www.ctan.org/pkg).其实从个人的使用上来讲，我还是推荐使用Latex的方式来编译，因为这种编译方式支持高清8的图片格式.eps.并且依赖包不用自己去下载。

2.设置表格等块中的本字体大小
可以在写了`\begin{xxxx}`紧跟着设置字体的大小，Latex设置字体大小的命令从小到大依次是:
 + \tiny
 + \scriptsize
 + \footnotesize
 + \small
 + \normal
 + \large
 + \Large
 + \LARGE
 + \huge
 + \Huge
因此在设置一个块内的字体大小一般可以写作类似于下面的形式:
```
\begin{table}[h]
\small
\begin{tabular}
\end{tabular}
\end{table}
```

3.Latex中图片、表的定位
一般Latex会为了排版效果自动的将某些在一页内放不下的图片或者表移动到一页可以放下的地方，因此，这就会出现将图片和表移到了不是你希望的地方。这时可以通过使用[H]将其位置定死，但是，这种方法的缺点就是如果一旦出现因为图片定死而导致某些页内被插入大量的空白，这事就得你自己调整了。示例代码如下:
```
\begin{figure}[H]
\centering
\includegraphics[width=0.4/textwidth]{figurename.eps}
\caption{xxxxxxxxx}
\end{figure}
```

