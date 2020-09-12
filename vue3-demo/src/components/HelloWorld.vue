<template>
  <div class="hello">
    <p>{{count}}</p>
    <button @click="count=231313">{{state.count}}</button>
    <datagrid>{{msg2}}</datagrid>
  </div>
</template>

<script>
// computed
import { reactive } from "vue"
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      x: 12,
      y: 20,
      msg2: "123",
    }
  },
  computed: {
    count: {
      get() {
        return this.x + this.y
      },
      set( ){
        this.msg2="adad"
        this.x="ada"
        this.y="重新的y"
      }
    },
  },
  setup() {
    const state = reactive({
      count: 0,
    })
    function add() {
      console.log("执行")
      state.count++
    }
    return {
      state,
      add,
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
</style>
