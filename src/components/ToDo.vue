<template>
    <div class="c-9kfy8p">
        <ToDoInput @add="handleAdd" />
        <ToDoList
            :list="list"
            @complete="handleComplete"
            @recover="handleRecover"
        />
    </div>
</template>

<script>
import { reactive } from 'vue';
import ToDoInput from './ToDoInput';
import ToDoList from './ToDoList';

let key = 1;

export default {
    components: { ToDoInput, ToDoList },
    setup() {
        const list = reactive([]);

        function handleAdd(content) {
            if (!content) return;
            list.push({ content, key: ++key, completed: false });
        }

        function handleComplete(index) {
            list[index].completed = true;
        }

        function handleRecover(index) {
            list[index].completed = false;
        }

        return { list, handleAdd, handleComplete, handleRecover };
    },
};
</script>

<style>
.c-9kfy8p {
    width: 600px;
    margin: 0 auto;
    padding: 80px 0;
}
</style>
