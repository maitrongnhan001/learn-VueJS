<template>
  <div class="task">
    <input type="checkbox" @change="task_data.done = !task_data.done">
    <span :class="{done: task_data.done}">{{task_data.content}}</span>
  </div>
</template>

<script>
export default {
   props: {
     task_data: {
        type: Object,
        default: function () {
          return {
            content: "null",
            done: false
          }
        }
     }
   },
   data () {
     return {
       content: "ABC"
     }
   }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .done {
    text-decoration: line-through;
  }
  input {
    margin-left: 30%;
  }
  span {
    margin-left: 10%;
  }
</style>
