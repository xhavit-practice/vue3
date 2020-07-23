<template>
    <div id="app">
        <ToDo />
    </div>
</template>

<script>
import ToDo from './components/ToDo';

export default {
    name: 'App',
    components: { ToDo },
};
</script>

<style>
* {
    margin: 0;
    padding: 0;
}
html,
input {
    font-family: Helvetica Neue, PingFang SC, Hiragino Sans GB, Heiti SC,
        Microsoft YaHei, WenQuanYi Micro Hei, sans-serif;
}
ul,
li {
    list-style: none;
}
</style>
