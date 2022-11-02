throw and System.exception(); 丟出例外訊息
---
```
try{
    if(符合條件){
        throw new System.Exception();//丟出新的例外訊息
    }
}cache{ //cache 捕捉任何例外訊息
    Console.WritLine("捕捉到符合條件的例外"); //執行捕捉到例外食的程式碼
}

//也可以限定其他類型的捕捉

 try {
            object o2 = null;
            int i2 = (int) o2; 
            System.Console.WriteLine(o2);
            System.Console.WriteLine(i2);
        }
        catch (System.NullReferenceException e) {//-------先判斷抓到沒有例外
            System.Console.WriteLine(e.ToString().Substring(0, 29));
        }
        catch {
            System.Console.WriteLine("something wrong");
        }finally {//--------------------無論有沒有抓到例外都會執行的部分
            System.Console.WriteLine("finally"); 
        }
```


==========

foreach
---
```
int [] a = new int[] { 25 , 18, 26};
int sum =0;
foreach(int i in a){
    sum+=i;
}

```
============

指標
---
```
unsafe{
    int* aPtr = &a;
    *aPtr=10;
    System.Console.WriteLine(*aPtr);
}

fixed 用於防止不安全的內容遭到記憶體重新配置，或是建立固定大小的緩衝區
unsafe static void Main() {
        Point pt = new Point();
        pt.x = 5;
        pt.y = 6;
 
        fixed (int* p = &pt.x) {
            SquarePtrParam(p);
        }
 
        System.Console.WriteLine ("{0} {1}", pt.x, pt.y);
    }
```
============================================================

enum 
---
```
enum 用來建立列舉型態，這是一種實值型態，簡單說就是依序遞增的整數數列或設定好的整數。

enum Days {Mon=1, Tue=2, Wed=3, Thu=4, Fri=5, Sat=6, Sun=7};

設定整數就是在識別字後面加上等號，自行指派整數值，例如

enum Days {Mon = 1, Tue, Wed, Thu, Fri, Sat, Sun};
// Mon = 1, Tue=2, Wed=3, Thu=4, Fri=5, Sat=6, Sun=7

```

============================================================

Dictionary
---
```
Key to Value 

如文字對應變數 效果跟Json類似


```
