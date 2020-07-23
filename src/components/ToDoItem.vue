<template>
    <div :class="{ 'c-2pcnu6-completed': data.completed }" class="c-2pcnu6">
        <div class="c-2pcnu6-content">{{ data.content }}</div>
        <div
            v-if="data.completed"
            class="c-2pcnu6-recover"
            @click="handleRecover"
        >
            恢复
        </div>
        <div v-else class="c-2pcnu6-complete" @click="handleComplete">
            完成
        </div>
    </div>
</template>

<script>
export default {
    props: {
        data: {
            type: Object,
            required: true,
        },
    },
    setup(props, { emit }) {
        function handleComplete() {
            emit('complete');
        }

        function handleRecover() {
            emit('recover');
        }

        return { handleComplete, handleRecover };
    },
};
</script>

<style>
.c-2pcnu6 {
    overflow: hidden;
    height: 40px;
    line-height: 40px;
    padding: 0 16px;
    background-color: #599cef;
    color: #fff;
    font-size: 14px;
    margin-top: 1px;
    transition: background-color 0.4s;
}
.c-2pcnu6:first-child {
    margin-top: 0;
    border-radius: 4px 4px 0 0;
}
.c-2pcnu6:last-child {
    border-radius: 0 0 4px 4px;
}
.c-2pcnu6-content {
    float: left;
}
.c-2pcnu6-recover,
.c-2pcnu6-complete {
    float: right;
    text-align: center;
    cursor: pointer;
}
.c-2pcnu6-completed {
    background-color: #71bb2e;
}
</style>
