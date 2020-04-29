<template>
    <div>
        <form @submit="addTodo">
            <input type="text" v-model="title" name="title" placeholder="Add Todo" class="todo-item">
            <input type="submit" value="Submit" class="btn">
        </form>
    </div>
</template>

<script>
//  import { uuid } from 'vue-uuid';

export default {
    name: "AddTodo",
    data(){
        return{
            title: ''
        }
    },
    methods: {
        addTodo(e){
            e.preventDefault();
            const newTodo = {
                title: this.title,
                completed: false
            }
            this.$emit('add-todo', newTodo);
            this.title = '';
        }
    }
}
</script>

<style scoped>
  .header {
    background: #333;
    color: #fff;
    text-align: center;
    padding: 10px;
  }
  .header a {
    color: #fff;
    padding-right: 5px;
    text-decoration: none;
  }
  .todo-item {
  width: 90%;
  padding: 12px 20px;
  margin: 0px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}
</style>