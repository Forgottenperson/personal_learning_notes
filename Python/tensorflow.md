# Python3 到深度學習過程

安裝 pip3(此為Python3)(需注意Python 3、Python 2版本問題)
---
wget https://bootstrap.pypa.io/get-pip.py  

python get-pip.py  

pip3  

---

Python工具
---
* matplotlib.pyplot   
* numpy  
* tensorflow
* virtualenv
---

numpy用法
---
```
import numpy as np

a=np.array([46,8,11,11,4,56])

print(a*30)

=>[1380 240 330 330 120 1680]
```

----

virtualenv 建立虛擬環境
---

建立 virtualenv --system-site-packages -p python3 ./venv

開啟虛擬環境 .\venv\Scripts\activate

關閉虛擬環境 .\venv\Scripts\deactivate  

----

tensorflow 筆記
---
```
x_train[..., tf.newaxis] x_train[tf.newaxis,...]

增加維度 可往前或後增加一維

使用前 shape [2,2]

使用後 shape [2,2,1]
```
```
將 tensorflow 2 切換至 tensorflow 1.xx

import tensorflow.compat.v1 as tf
tf.disable_v2_behavior()
```