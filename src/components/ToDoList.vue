<template>
    <div class="c-rfrz7u">
        <ToDoItem
            class="c-rfrz7u-item"
            v-for="(item, index) in list"
            :key="item.key"
            :data="item"
            @complete="handleComplete(index)"
            @recover="handleRecover(index)"
        />
    </div>
</template>

<script>
import ToDoItem from './ToDoItem';

export default {
    components: { ToDoItem },
    props: {
        list: {
            type: Array,
            default: () => [],
        },
    },
    setup(props, { emit }) {
        function handleComplete(index) {
            emit('complete', index);
        }

        function handleRecover(index) {
            emit('recover', index);
        }

        return { handleComplete, handleRecover };
    },
};
</script>

<style>
.c-rfrz7u {
    margin-top: 8px;
}
</style>
