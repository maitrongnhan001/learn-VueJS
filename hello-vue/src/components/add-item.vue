<template>
  <div class="add-item">
    <input type="text" v-model="new_task">
    <button @click="add_task" >Add task</button>
  </div>
</template>

<script>
export default {
    props: {
        add_item: {
            type: Function
        }
    },
    data () {
        return {
            new_task: ""
        }
    },
    methods: {
        add_task: function () {
            this.add_item(this.new_task)
        }
    }
}
</script>

<style scoped>
input {
    width: 75%;
    height: 35px;
    border: 1px solid green;
    border-radius: 5px;
    margin: 0 2% 2% 0;
}
button {
    width: 20%;
    height: 38px;
    color: white;
    background: green;
    border-radius: 5px;
    border: 0;
}
</style>