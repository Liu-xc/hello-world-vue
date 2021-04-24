<template>
  <div>
    <div>{{ title }}</div>
    <div>
      <el-switch v-model="itemDone"></el-switch>
    </div>
  </div>
</template>

<script>
export default {
  // TODO 展示title和状态
  props: {
    title: String,
    done: Boolean,
  },
  data () {
    return {
      itemDone: this.done,
    }
  },
  watch: {
    itemDone () {
      this.$emit('itemStateChange');
    }
  }
}
</script>

<style>
</style>