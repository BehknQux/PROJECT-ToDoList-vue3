<template>
<div>
    <!-- <label for="mainput"></label> -->
    <input v-model="todoText" @keydown.enter="addNewTodo(todoText)" class="form-control bg-dark border-bottom text-light my-5 rounded-0" id="mainput" type="text" placeholder="bir şeyler yazınız">
</div>
</template>

<script>
export default {
    props: {
        addNewTodo: {
            type: Function,
            required: true
        }
    },
    data() {
        return {
            todoText: null
        }
    },
    methods: {
        // addtodo(){
        //     this.$emit("add-todo",this.todoText);
        //     this.todoText = null
        // }
    }
}
</script>

<style>
body {
    background-color: #212429 !important;
}

#todotext {
    margin-right: 1rem;
}

#mainput::placeholder {
    color: #ffc107;
}
</style>
