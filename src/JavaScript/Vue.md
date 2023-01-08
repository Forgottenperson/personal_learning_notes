
要從js 傳遞資料至 html內需要 data()的function回傳json格式


```
<script>
export default {
  data(){
    return{
  		message:'Hello world'
		}
  }
}
</script>

<template>
  <h1>{{ message }}</h1>
</template>
```

* v-bind:id="dynamicId"或是:id="dynamicId"來進行動態綁定參數

例如將css版型設定當作js參數傳至前端的class裡

```
createApp({
  data() {
    return {
      titleClass: 'title'
    }
  }
}).mount('#app')
</script>

<div id="app">
  <h1 :class="titleClass">Make me red</h1>
</div>

.title {
  color: red;
}
```

* v-on 用來建立js event v-on:click="increment" 或是 @click="increment"

```
<script>
export default {
  data() {
    return {
      count: 0
    }
  },
  methods: {
    increment() {
      this.count++
    }
  }
}
</script>

<template>
  <button @click="increment">count is: {{ count }}</button>
</template>
```

* v-model 本質上是語法糖 為v-on v-bind同時使用
當需要同時將資料輸入並顯示在網頁上的雙向資料傳輸與綁定時可以使用此簡寫


```
<script>
export default {
  data() {
    return {
      text: ''
    }
  },
  methods: {
    onInput(e) {
      this.text = e.target.value
    }
  }
}
</script>

<template>
  <input :value="text" @input="onInput" placeholder="Type here">
  <p>{{ text }}</p>
</template>
```

* v-if v-else 當v-if的判斷是為true時則會顯示該行 反之亦然

```
<script>
export default {
  data() {
    return {
      awesome: true
    }
  },
  methods: {
    toggle() {
      this.awesome = !this.awesome
    }
  }
}
</script>

<template>
  <button @click="toggle">toggle</button>
  <h1 v-if="awesome">Vue is awesome!</h1>
  <h1 v-else>Oh no 😢</h1>
</template>
```

* v-for :key 為Vue網頁端的迴圈使用

```
<ul>
  <li v-for="todo in todos" :key="todo.id">
    {{ todo.text }}
  </li>
</ul>

```

* computed 放置的是僅僅只是計算當中的內容並將結果返回至網頁端但不修改放置其中的變數

```
<script>
let id = 0

export default {
  data() {
    return {
      newTodo: '',
      hideCompleted: false,
      todos: [
        { id: id++, text: 'Learn HTML', done: true },
        { id: id++, text: 'Learn JavaScript', done: true },
        { id: id++, text: 'Learn Vue', done: false }
      ]
    }
  },
  computed: {
    filteredTodos() {
      return this.hideCompleted
        ? this.todos.filter((t) => !t.done)
        : this.todos
    }
  },
  methods: {
    addTodo() {
      this.todos.push({ id: id++, text: this.newTodo, done: false })
      this.newTodo = ''
    },
    removeTodo(todo) {
      this.todos = this.todos.filter((t) => t !== todo)
    }
  }
}
</script>

<template>
  <form @submit.prevent="addTodo">
    <input v-model="newTodo">
    <button>Add Todo</button>
  </form>
  <ul>
    <li v-for="todo in filteredTodos" :key="todo.id">
      <input type="checkbox" v-model="todo.done">
      <span :class="{ done: todo.done }">{{ todo.text }}</span>
      <button @click="removeTodo(todo)">X</button>
    </li>
  </ul>
  <button @click="hideCompleted = !hideCompleted">
    {{ hideCompleted ? 'Show all' : 'Hide completed' }}
  </button>
</template>

<style>
.done {
  text-decoration: line-through;
}
</style>
```

* ref 可以讓你在js內直接修改原生的DOM

```
<script>
export default {
  mounted() {
    this.$refs.p.textContent='tt'
  }
}
</script>

<template>
  <p ref="p">hello</p>
</template>
```

* watch 可以觀測變數的變化來執行function

```
data() {
    return {
      todoId: 1,
      todoData: null
    }
  },
watch: {
  	todoId(newCount){
      console.log(`new count is: ${newCount}`);
    }
  }
```

* components 相等於 Angularjs 的 directive 可以自定義標籤

```
export default {
  components: {
    ChildComp
  }
}

<ChildComp />
```

* Props 取得標籤所放入的 arguments

```
export default {
  components: {
    ChildComp
  },
  data() {
    return {
      greeting: 'Hello from parent'
    }
  }
}
</script>

<template>
  <ChildComp :msg="greeting"/>
</template>
```

* emits 跟使用Props目的相反
將 components 內的參數傳出到父物件

```
export default {
  components: {
    ChildComp
  },
  data() {
    return {
      childMsg: 'No child msg yet'
    }
  }
}
</script>

<template>
  <ChildComp @response="(msg) => childMsg = msg" />
  <p>{{ childMsg }}</p>
</template>
```

```
export default {
  emits: ['response'],
  created() {
    this.$emit('response', 'hello from child')
  }
}
</script>

<template>
  <h2>Child component</h2>
</template>
```

* slot 可以從子元件修改父元件使用的內容

```
<template>
  <ChildComp></ChildComp>
</template>
```

```ChildComp
<template>
  <slot>Fallback content</slot>
</template>
```