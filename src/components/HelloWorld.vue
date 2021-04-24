<template>
  <div class="hello">
    <el-button type="primary">hello</el-button>
  </div>
</template>

<script>
// TODO 这里能不能不用default导出
export default {
  name: "HelloWorld",
  props: {
    msg: String,
    name: {
      type: String,
      default: "jmc",
    },
    obj: {
      type: Object,
      default: () => {
        return {
          a: 1,
        };
      },
    },
  },
  data () {
    return {
      isRed: true,
      firstName: "lkfajs;dkasld",
      lastName: "",
    };
  },
  beforeCreate () {
    // this.data
  },
  created () {
    console.log("created");
    this.hello();
    console.log(this.fullName);
  },
  methods: {
    hello () {
      console.log("hello");
    },
    onClickName () {
      // 触发事件
      this.$emit("clickName", "newName");
    },
  },
  watch: {
    // 监听
    firstName (newval, oldval) {
      console.log("watch", newval, oldval);
      // 在这里作一些事情，但不用返回值，也不是属性
      // 在这里重新计算
    },
    lastName () { },
  },
  computed: {
    // 计算属性,一定要返回值，因为它是一个属性
    fullName () {
      return this.firstName + this.lastName;
    },
    age () {
      return 1;
    },
    list () {
      return ["box", this.isRed ? "red-box" : ""];
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

.box {
  width: 100px;
  height: 100px;
  background: #42b983;
}
.red-box {
  background: red;
}
</style>
