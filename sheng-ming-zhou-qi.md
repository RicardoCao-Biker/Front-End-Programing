Vue共有8个生命周期钩子函数，分别为：

* beforeCreate el 和 data 并未初始化均为undefined

* created 完成了 data 数据的初始化，el没有初始化

* beforeMount 完成了el初始化,但data并没有挂载完成

* mounted 完成了挂载

* beforeUpdate 数据更新之前

* updated 数据更新之前

* beforeDestroy 实例销毁之前，在这一步，实例仍然完全可用

* destroyed Vue 实例销毁后，Vue 实例指示的所有东西都会解绑定



