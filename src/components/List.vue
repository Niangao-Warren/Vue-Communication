<template>
  <div>
    <ul>
      <li v-for="item in list" :key="item.id">
        {{item.title}}
        <button @click="deleteItem(item.id)">删除</button>
      </li>
    </ul>
  </div>
</template>

<script>
import event from '../event'
export default {
  props: {
    // 用来接收父组件传给子组件的数据
    list: {
      type: Array,
      default() {
        return []
      }
    }
  },
  methods: {
    // 调用父组件的事件
    deleteItem(id) {
      this.$emit('delete', id)
    },
    addTitleHandler(title) {
      console.log('on add title', title)
    }
  },
  mounted() {
    // 绑定自定义事件
    event.$on('onAddTitle', this.addTitleHandler)
  },
  beforeDestroy() {
    // 及时销毁，否则可能会造成内存泄漏
    event.$off('onAddTitle', this.addTitleHandler)
  },
}
</script>