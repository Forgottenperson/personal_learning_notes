Array
---
Array(9).fill(1);

填滿陣列

---

jsx
---
jsx 能夠在javascript 使用HTML標籤的格式

return HTML格式

在HTML格式中使用變數需加 { }

HTML格式是直接傳入，不須當字元
```
const element = <img src={url} />;
```
需要將多行HTML當成變數時，要加上括弧
```
const s=(
  <h1>
      Hello world
  </h1>
)
```

---

React XSS injection protection (待確認)
---
React 預設會在render之前將嵌入jsx的變數清除，防止被任何注入式攻擊
所有變數都會轉成字串，可以預防XSS攻擊

因此故能直接將變數傳入至網頁(待確認)


---


React 最小單位為element 並且是 immutable 
```
const element = <img src={url} />;
```

---

React.Component
---
常使用的function
* this.state 與 setState()
* this.props
* \<li key={move}>\</li>
* componentDidMount() 與 componentWillUnmount()




假設有一個功能 Square 下方為其使用方式
```
renderSquare(i) {
    return <Square 
             value={this.state.squares[i]} 
             onClick={()=>this.change(i)} 
             />;
  }

```


當需定義出的功能不使用state時

```
class Square extends React.Component {
  render() {
    return (
      <button 
        className="square" 
        onClick={() => this.props.onClick()}>
        {this.props.value}
      </button>
    );
  }
}
```

可以改用 function 來取代 class 當作 HTML標籤 以簡化結構

```
function Square(props) {
  return (
    <button className="square" onClick={props.onClick}>
      {props.value}
    </button>
  );
}
```


React.memo 
---
若每次render出相同結果可以改用memo來藉此加速