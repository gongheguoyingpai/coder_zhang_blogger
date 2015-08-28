Linux如何找到进程的工作目录
------------------------------------

首先找到进程id
```
ps aux | grep  process_name
```

这样会找到进程的id

然后利用进程id来查找进程的工作目录即可:
```
pwdx process_id
```
