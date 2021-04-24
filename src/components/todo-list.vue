<template>
  <div>
    TodoList
    <todo-item
      @itemStateChange="onChange(index)"
      v-for="(item, index) of list"
      :key="item.title"
      :title="item.title"
      :done="item.done"
    ></todo-item>
  </div>
</template>

<script>
import TodoItem from './todo-item';
export default {
  components: {
    TodoItem
  },
  data () {
    return {
      list: [
        {
          title: '123',
          done: true,
        },
        {
          title: '1234',
          done: true,
        },
        {
          title: '1235',
          done: true,
        }
      ]
    }
  },
  methods: {
    onChange (index) {
      // TODO 在这里修改list
      this.list[index].done = !this.list[index].done;
      console.log(this.list[index]);
    }
  },
}
</script>

<style>
</style>