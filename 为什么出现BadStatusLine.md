在使用python的urllib2进行网络请求时，出现了BadStatusLine的异常，
这种异常之前从没有见到过，记录一下。

可以看到BadStatusLine的异常是从httplib.py这个python自带的标准库
件中抛出，因为python的代码是开源的，所以，我们可以查看一下该文件的
源代码.

[httplib.py](https://hg.python.org/cpython/file/2.7/Lib/httplib.py)

可以看到，该异常的抛出是在第417行附近:
```python
if not line:
    # Presumbly, the server closed the connection before
    # sending a valid response
    raise BadStatusLine(line)
```

所以，从注释中我们可以比较清晰的看到，问题的原因是在服务器返回数据之前
就关闭了连接，那么最可能的原因就是对于某些请求，服务器端接受了请求，但是
却没有任何的数据返回，从而导致出现了该问题。
