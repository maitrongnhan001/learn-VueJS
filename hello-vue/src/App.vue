<template>
  <div id="app">
    <div class = "app">
      <addItem :add_item="add_task"></addItem>
      <item v-for="(task, index) in tasks" :key="index" :task_data="task"></item>
      {{total | format_total}}
      <button @click="add_total()">+20000</button>
    </div>
  </div>
</template>

<script>
import item from './components/Item.vue';
import addItem from './components/add-item.vue';

export default {

  name: 'App',
  data() {
    return {
      tasks: [
        { content: 'di cho', done: false },
        { content: 'nau an', done: false },
        { content: 'code', done: false },
        { content: 'sleep', done: false }
     ],
     total: 1000000000
    }
  },
  filters: {
    format_total: function (total) {
      var cal_total = total.toString();
      let i = cal_total.length - 3;
      while (i > 0) {
        cal_total = cal_total.slice(0, i) + '.' + cal_total.slice(i);
        i -= 3;
      }
      return cal_total;
    }
  },
  methods: {
     add_task: function (data) {
       this.tasks.push({content: data, done: false})
     },  
     add_total: function () {
       this.total += 20000
     }
  }
  ,
  components: {
    item,
    addItem
  }
}
</script>

<style scoped>
  .choose {
    color: red;
  }
  #app {
    width: 100%;
    height: 100%;
  }
  .app {
    width: 500px;
    margin: 0 auto;
  }
</style>
