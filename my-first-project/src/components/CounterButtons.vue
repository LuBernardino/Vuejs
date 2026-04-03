<template>
    <div class="buttons">
        <h3>Valor atual de Count: {{countValue}}</h3>
        <MyButton 
            title="Soma +1"
            @update="$emit('change-count', 'increment', 1)"
        />
        <MyButton 
            title="Subtração -1" 
            :disabled="!canDecrement"
            @update="$emit('change-count', 'decrement', 1)"
        />
        <MyButton 
            title="Resetar"
            :disabled="!canReset"
            @update="$emit('change-count', 'reset', 1)"
        />
    </div>
</template>

<script>
import MyButton from './MyButton';
export default {
    name: 'CounterButtons',
    emits: ['change-count'],
    components: {
        MyButton
    },
    props: {
        countValue: {
            type: Number,
            required: true,
        }
    },
    computed: {
        canDecrement() {
            return this.countValue > -10
        },
        canReset() {
            return this.countValue !== 0
        }
    }
}
</script>

<style>
.buttons {
    display: flex;
    gap: 10px;
    background-color: #e9eff1;

    padding: 10px;
    border-radius: 6px;
}
</style>