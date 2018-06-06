#### 父组件向子组件通信

使用props，父组件可以使用props向子组件传递数据。

```
//父组件
<template>
    <child :msg="message"></child>
</template>

<script>

import child from './child.vue';

export default {
    components: {
        child
    },
    data () {
        return {
            message: 'father message';
        }
    }
}
</script>
//子组件
<template>
    <div>{{msg}}</div>
</template>

<script>
export default {
    props: {
        msg: {
            type: String,
            required: true
        }
    }
}
</script>

```

#### 子组件向父组件通信

使用vue事件，父组件向子组件传递事件方法，子组件通过$emit触发事件，回调给父组件。

```
//父组件
<template>
    <child @msgFunc="func"></child>
</template>

<script>

import child from './child.vue';

export default {
    components: {
        child
    },
    methods: {
        func (msg) {
            console.log(msg);
        }
    }
}
</script>
//子组件
<template>
    <button @click="handleClick">点我</button>
</template>

<script>
export default {
    props: {
        msg: {
            type: String,
            required: true
        }
    },
    methods () {
        handleClick () {
            //........
            this.$emit('msgFunc');
        }
    }
}
</script>
```

#### 非父子组件、兄弟组件之间的数据传递

非父子组件通信，Vue官方推荐使用一个Vue实例作为中央事件总线。 $on方法用来监听一个事件。

$emit用来触发一个事件。

```
/*新建一个Vue实例作为中央事件总嫌*/
let event = new Vue();

/*监听事件*/
event.$on('eventName', (val) => {
    //......do something
});

/*触发事件*/
event.$emit('eventName', 'this is a message.');
```

  


