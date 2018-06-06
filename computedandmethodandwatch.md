#### cpmputed/method

```
<p>Reversed message: "{{ reversedMessage() }}"</p>

// 在组件中
methods: {
  reversedMessage: function () {
    return this.message.split('').reverse().join('')
  }
}
```

* 计算属性只有在它的相关依赖发生改变时才会重新求值。这就意味着只要`message`还没有发生改变，多次访问`reversedMessage`计算属性会立即返回之前的计算结果，而不必再次执行函数。

* 使用：原始数据经过处理得到结果。计算属性默认只有 getter 。

### watch

watch是监控一个对象，当变化时执行操作

```
<div id="watch-example">
  <p>
    Ask a yes/no question:
    <input v-model="question">
  </p>
  <p>{{ answer }}</p>
</div>
```

    var watchExampleVM = new Vue({
      el: '#watch-example',
      data: {
        question: '',
        answer: 'answer'
      },
      watch: {
        // 如果 `question` 发生改变，这个函数就会运行
        question: function (newQuestion, oldQuestion) {
          this.answer = 'Waiting for you to stop typing...'
          this.debouncedGetAnswer()
        }
      }
    }

  


