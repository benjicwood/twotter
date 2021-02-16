<template>
    <div class="twoot-item" @click="favouriteTwoot(twoot.id)">
        <div>@{{username}}</div>
        <div>{{ twoot.content }}</div>
    </div>
</template>

<script>
export default {
    name: 'TwootItem',
    props: {
        username: {
            type: String,
            required: true,
        },
        twoot: {
            type: Object,
            required: true,
        }
    },
    methods: {
        favouriteTwoot(id) {
            this.$emit('favourite', id);
        }
    }
}
</script>

<style scoped>
.twoot-item {
    padding: 20px;
    background-color: whitesmoke;
    border: 1px solid black;
    border-radius: 5px;
    box-sizing: border-box;
    cursor: pointer;
    transition: all 0.25s ease;
}
.twoot-item:hover {
    transform: scale(1.1, 1.1);
}
</style>