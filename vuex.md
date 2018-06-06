### State

从 store 实例中读取状态最简单的方法就是在计算属性中返回某个状态

    //每当 store.state.count 变化的时候, 都会重新求取计算属性，并且触发更新相关联的 DOM。
    const Counter = {
      template: `
    <
    div
    >
    {{ count }}
    <
    /div
    >
    `,
      computed: {
        count () {
          return store.state.count
        }
      }
    }

### Getter

Vuex 允许我们在 store 中定义“getter”（可以认为是 store 的计算属性）。就像计算属性一样，getter 的返回值会根据它的依赖被缓存起来，且只有当它的依赖值发生了改变才会被重新计算。

* Getter 接受 state 作为其第一个参数：

```
const store = new Vuex.Store({
  state: {
    todos: [
      { id: 1, text: '...', done: true },
      { id: 2, text: '...', done: false }
    ]
  },
  getters: {
    doneTodos: state =
>
 {
      return state.todos.filter(todo =
>
 todo.done)
    }
  }
})
```

### Mutation

更改 Vuex 的 store 中的状态的唯一方法是提交 mutation

**Mutation 必须是同步函数**

```
const store = new Vuex.Store({
  state: {
    count: 1
  },
  mutations: {
    increment (state) {
      // 变更状态
      state.count++
    }
  }
})
//通过commit来调用mutation中的方法
store.commit('increment')
```

### Action

* Action 提交的是 mutation，而不是直接变更状态。

* Action 可以包含任意异步操作。

```
const store = new Vuex.Store({
  state: {
    count: 0
  },
  mutations: {
    increment (state) {
      state.count++
    }
  },
  actions: {
    increment (context) {
      context.commit('increment')
    }
  }
})
//Action 通过 store.dispatch 方法触发：
store.dispatch('increment')
```

### Module

Vuex 允许我们将 store 分割成**模块（module）**。每个模块拥有自己的 state、mutation、action、getter

