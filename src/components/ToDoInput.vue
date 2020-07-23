<template>
    <div class="c-a75vq0">
        <input
            class="c-a75vq0-input"
            placeholder="按enter键添加待办事项"
            @input="handleInput"
            @keyup.enter="handleEnter"
            :value="content"
        />
    </div>
</template>

<script>
import { ref } from 'vue';

export default {
    props: {},
    setup(props, { emit }) {
        const content = ref('');

        function handleInput(e) {
            content.value = e.target.value;
        }

        function handleEnter() {
            emit('add', content.value);
            content.value = '';
        }

        return { content, handleInput, handleEnter };
    },
};
</script>

<style>
.c-a75vq0-input {
    display: block;
    width: 100%;
    box-sizing: border-box;
    border: 1px solid #599cef;
    line-height: 38px;
    padding: 0 16px;
    outline: none;
    border-radius: 4px;
    font-size: 14px;
    transition: box-shadow 0.4s;
}
.c-a75vq0-input:focus {
    box-shadow: 0 0 5px 4px rgba(89, 156, 239, 0.25);
}
</style>
