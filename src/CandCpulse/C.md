C
---


pointer
---
```
int b=5;
int* a=&b;

char* a="abcdefg";
```
malloc sizeof
---

String
---
* strcpy(a,b)-copy b into a
* strcat(a,b)-合併字串 b 到 a 的 尾端
* strlen(a)-a的字串長度
* strcmp(a,b)-判斷a跟b是否相同，相同則為0，不相同a>b 大於1，a<\b 則小於1 
* strchr(a,b)-回傳指標 尋找在a字串中有'b'的第一個指標位置
* strstr(a,b)-回傳指標 尋找在a字串中有b字串變數內容的第一個指標位置


array
---
```
int array[]={1,2,3,4}
```


struct
---
```
struct a {
   int i;
   float f;
} b;  
```



union
---
```
union Data {
   int i;
   float f;
} data;  
```

typedef #define(Macros)
---
* #define(Macros)
    * pre-processor
* typedef 
    * compiler 



(a.h a.c)->pre-processor->Compiler->(a.o ... .o) -> linker -> exe(a.out)

other
---
* Vector
* Queue
* Stack
* Set
* Map