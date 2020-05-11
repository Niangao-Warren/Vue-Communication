# Vue 的组件通信

- 父组件通过 `props` 给子组件传值
- 子组件通过 `vm.$emit(event, arg)` 触发父组件事件
- 其他组件通过 `vm.$on( event, fn )` 进行通信，实例一个 `Vue` 实例 `event` 作为媒介，在要相互通信的组件中引入 `event`

关于该项目的讲解，可参考该篇博文：[Vue 组件通信](https://www.jianshu.com/p/ac2886b9f6bf)