<template>
<div>
    <ul class="list-group rounded-0">

        <!-- BURADA BİR ŞEYLERİ BOZDUK -->

        <TodoListItem @delete-todo-item="$emit('delete-todo-item',$event)" v-for="todo in mydata" :key="todo.id" :item="todo"  />
        <!-- <li class="d-flex align-items-center justify-content-between list-group-item bg-warning text-dark my-1">
            <span id="todotext" class="border border-dark p-1 d-flex flex-wrap"></span>
            <button class="btn btn-dark text-warning rounded-0">SİL</button>
        </li> -->
        {{ todolist }}
    </ul>
</div>
</template>
<script>

import TodoListItem from "@/components/TodoListItem";
export default {
    props: ["mydata"],
    components:{
        TodoListItem
    }
}

</script>