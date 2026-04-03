<template>
    <button @click="$emit('update')">
        {{ title }}
    </button>
</template>

<script>
    export default {
        name: 'MyButton',
        props: {
            title: {
                type: String,
                default: '+1'
            }
        }
    }
</script>

<style>
    button {
        width: auto;
        padding: 10px 13px;
        
        background-color: #42b983;
        color: white;
        border: none;
        border-radius: 8px;
        cursor: pointer;

        font-size: 16px;

        &:hover {
            background-color: red;
        }
    }

</style>