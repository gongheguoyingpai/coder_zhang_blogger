# TensorFlow模型保存与加载、冻结

### TensorFlow加载预训练模型
```
tvars = tf.trainable_variables()
init_vars = tf.train.list_variables(init_checkpoint)
init_var_names = [var[0] for var in init_vars]
assignment_map = {}
for var in tvars:
    var_name = var.name
    if "part_" in var_name:
        var_name = var_name[:var_name.find("/part_")]
    if var_name.endswith(":0"):
        var_name = var_name[:-2]
    if var_name in init_var_names:
        assignment_map[var_name] = var_name
tf.train.init_from_checkpoint(init_checkpoint, assignment_map)
```

### 冻结模型参数
这里记录三种方法:
#### 通过将变量设置trainable=False达到冻结参数的目的
通过将变量设置为trainable=False，在训练时就不会将相应的变量放入到GraphKeys.TRAINABLE_VARIABLES中，所以在训练时也就不会对相应的参数进行更新。

#### 使用tf.stop_gradient函数
对于不想进行更新的参数，可以在其上使用该函数，比如
```python
w1 = tf.stop_gradient(w1)
```
在进行模型训练时就不会对w1中的参数进行更新。

#### optimizer.compute_gradients或者optimizer.minimize函数
调用optimizer.compute_gradients或者optimizer.minimize函数，允许我们指定要更新的变量列表，所以如果希望只更新某些变量，就可以在调用这两个函数的同时只指定希望更新的变量列表。默认情况，更新的变量列表对应GraphKeys.TRAINABLE_VARIABLES中的所有变量。

#### tf.train.init_from_checkpoint
https://www.tensorflow.org/api_docs/python/tf/train/init_from_checkpoint

### 参考文章
- TensorFlow API(4) save/restore: https://irvingzhang0512.github.io/2018/04/30/tensorflow-api-4/
- Tensorflow冻结变量方法: https://www.cnblogs.com/hrlnw/p/10400057.html
- Tensorflow Finetune方法: https://zhuanlan.zhihu.com/p/42183653
- Tensorflow冻结部分层，只训练某一层: https://blog.csdn.net/b876144622/article/details/79962759
- 