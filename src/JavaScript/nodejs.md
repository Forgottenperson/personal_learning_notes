Immutability 不可變性 相關function
---
```
Object.assign
array.map
array.filter 
array.concat
array.slice
```

mutability 可變性
---
```
array.push 
array.pop 
array.sort
array.splice
```


spread syntax
---
```
let i=[1,2,3,4,5]
let j=[...i,6]

```


Promise
---
```
new Promise(resolve,reject);

resolve=function(res){
    res();
}

reject=function(rej){

}
```


async/await
---
```
async test(){
    await new Promise(resolve);//會等到resolve內res()執行後才會繼續執行
}
```

```
async test(){
    return 1;
}

跟

async test(){
    return Promise.resolve(1);
}

是相同的
```

---
```
new出的子物件的__proto__為父function的prototype
```


Event Loop
---
```
由於js引擎為Single Theard，故為了能達到異步效果，
會先將async setTimeout 等需要異步執行的丟到事件佇列(Event Queue)，當主Thread(Stack)執行完成後，
才會再去執行事件佇列(Event Queue)的程式，當事件佇列(Event Queue)執行完成後，再回到主Thread(Stack)執行，
先堆疊(Stack)後事件佇列(Event Queue)再回堆疊(Stack)，這個過程為Event Loop
```


polyfill  Transpiler
---