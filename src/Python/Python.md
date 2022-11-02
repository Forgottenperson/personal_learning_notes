# Python3 基礎

安裝 pip3(此為Python3)(需注意Python 3、Python 2版本問題)
---
wget https://bootstrap.pypa.io/get-pip.py  
python get-pip.py  
pip3  

---

Python工具
---
* matplotlib.pyplot 
* Matplotlib   
* numpy  
* (python-)tk(圖形介面)  
* import Tkinter
---

---

其他判斷
---
```
len():長度 (PS 字串可以用)
type():類型
```

變數轉換
---

```
可以這樣用
a="hello"
print(a[2])
答案會是
hello的l

float()：轉換變數類型為 float
int()：轉換變數類型為 int
complex()：轉換變數類型為 complex (虛數)
bool()：轉換變數類型為 bool
str()：轉換變數類型為 str
113.0625
round(_, 2)
113.06
```

----

資料結構 List,Tuple and Dictionary  
===

List  
---
my_List = [1,2,3,4,5] #跟陣列很像

a.insert():(插入位置:資料) PS. a.insert(5,"SS")  



tuple  
---
跟List很像 無法新增修改刪除 用 tuple() 轉換  

---

dictionary
---
```
a_dic = {
    "X": True,
    "Y": 1,
    "Z": "XXAA"
}#類似json格式

print(a_div["x"])#這裡是[]中括弧

```
range() 函式 #生成等差級數

---

for 陳述式
---
```
for 還有另一種接近類似try cache

for int i in range(5):
    if 符合條件
        break
else:
    #每當程式執行完一次未跳離迴圈(break)
    print("顯示")

```

---

if 陳述式
---
```

if x>0:
    print("X是正數")
elif x==0:
    print("X為0")
else x<0:
    print("X為負數")

```

---

while 陳述式
---
```
while b<10:
    print("X")
    b++
```

---
