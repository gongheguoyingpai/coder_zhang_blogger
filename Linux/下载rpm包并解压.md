下载rpm包并解压
-----------------------------------

有时，我们可能并不想安装一个RPM包，而仅仅是想知道在这个包里面有哪些内容。
这时就会涉及到对rpm包从rpm源的下载和解压问题。

#####下载RPM包

```
yumdownloader rpm包名
```
这样，会将rpm包下载到当前的目录下。


#####解压RPM包

```
rpm2cpio 下载的rpm包  | cpio -div
```
即可将下载的rpm包解压到当前目录下，之后就可以查看在解压出的件夹下查看有什么内容啦!

