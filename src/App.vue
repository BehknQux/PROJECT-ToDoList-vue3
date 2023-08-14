<template>
<div class="container text-warning">
    <hr>
    <h1 class="">PROJECT: ToDo</h1>
    <hr>
    <div>
        <div class="d-flex justify-content-center align-items-center flex-column">
            <AddSection :addNewTodo="addNewTodo" ref="addsection"/>
            <!-- <input @keydown.enter="ant" class="form-control bg-dark border-bottom text-light my-5 rounded-0" id="mainput" type="text" placeholder="bir şeyler yazınız"> -->
            <TodoList :mydata="todolist" @delete-todo-item="deleteItem"/>
            <!-- <ul class="list-group rounded-0">
                <li v-for="todo in todolist" :key="todo.id" class="d-flex align-items-center justify-content-between list-group-item bg-warning text-dark my-1">
                    <span id="todotext" class="border border-dark p-1 d-flex flex-wrap">{{ todo.text }}</span>
                    <button @click="deleteitem(todo)" class="btn btn-dark text-warning rounded-0">SİL</button>
                </li>
            </ul> -->
        </div>
    </div>
</div>
</template>

<script>
import AddSection from "@/components/AddSection";
import TodoList from "@/components/TodoList";
export default {
    components: {
        AddSection,
        TodoList
    },
    created(){
            this.todolist = [{
                    id: 1,
                    text: "Bootcamp #1"
                },
                {
                    id: 2,
                    text: "Bootcamp #2"
                },
                {
                    id: 3,
                    text: "Bootcamp #3"
                },
            ]
    },
    data() {
        return {
            todolist:[],
        }
    },
    methods: {
        
        deleteItem(todoItem) {
            this.todolist = this.todolist.filter((t) => t !== todoItem);
        },
        addNewTodo(todo) {
            this.todolist.push({
                id: new Date().getTime(),
                text: todo
            });
            this.$refs.addsection.todoText = null;
        }
    },
}
</script>

<style>

</style>
