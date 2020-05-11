<template>
  <div>
    <input type="text" v-model="title"/>
    <button @click="addTitle">添加</button>
  </div>
</template>
<script>
import event from '../event'
export default {
  data() {
    return {
      title: ''
    }
  },
  methods: {
    addTitle() {
      // 调用父组件的事件
      this.$emit('add', this.title)
      // 调用自定义事件
      event.$emit('onAddTitle', this.title)
      this.title = ''
    }
  }
}
</script>