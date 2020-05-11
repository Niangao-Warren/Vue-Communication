<template>
  <div id="app">
    <Input @add="addHandler"/>
    <List :list="list" @delete="deleteHandler"/>
  </div>
</template>

<script>
import Input from './components/Input'
import List from './components/List'
export default {
  data() {
    return {
      list: [
        {
          id: 'id-1',
          title: 'title-1'
        },
        {
          id: 'id-2',
          title: 'title-2'
        }
      ]
    }
  },
  methods: {
    addHandler(title) {
      this.list.push({
        id: `id-${Date.now()}`,
        title
      })
    },
    deleteHandler(id) {
      this.list = this.list.filter(item => item.id !== id)
    }
  },
  components: {
    List,
    Input
  }
}
</script>
