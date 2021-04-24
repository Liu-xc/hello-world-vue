<template>
  <div>
    <h1>TodoApp</h1>
    <search></search>
    <process></process>
    <order></order>
    <todo-list></todo-list>
  </div>
</template>

<script>
import Order from '../components/order';
import Process from '../components/process';
import Search from '../components/search';
import TodoList from '../components/todo-list';

export default {
  components: {
    Order,
    Process,
    Search,
    TodoList
  }
}
</script>

<style>
</style>