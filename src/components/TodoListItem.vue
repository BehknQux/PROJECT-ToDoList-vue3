<template lang="">
    <div>
        
        <li class="d-flex align-items-center justify-content-between list-group-item bg-warning text-dark my-1">
            <span id="todotext" class="border border-dark p-1 d-flex flex-wrap">{{item.text}}</span>
            <button @click="$emit('delete-todo-item',item)" class="btn btn-dark text-warning rounded-0">SİL</button>
        </li>
    </div>
</template>
<script>
    export default {
        props: ["item"]
    }
</script>