��ʹ��python��urllib2������������ʱ��������BadStatusLine���쳣��
�����쳣֮ǰ��û�м���������¼һ�¡�

���Կ���BadStatusLine���쳣�Ǵ�httplib.py���python�Դ��ı�׼��
�����׳�����Ϊpython�Ĵ����ǿ�Դ�ģ����ԣ����ǿ��Բ鿴һ�¸��ļ���
Դ����.

[httplib.py](https://hg.python.org/cpython/file/2.7/Lib/httplib.py)

���Կ��������쳣���׳����ڵ�417�и���:
```python
if not line:
    # Presumbly, the server closed the connection before
    # sending a valid response
    raise BadStatusLine(line)
```

���ԣ���ע�������ǿ��ԱȽ������Ŀ����������ԭ�����ڷ�������������֮ǰ
�͹ر������ӣ���ô����ܵ�ԭ����Ƕ���ĳЩ���󣬷������˽��������󣬵���
ȴû���κε����ݷ��أ��Ӷ����³����˸����⡣
