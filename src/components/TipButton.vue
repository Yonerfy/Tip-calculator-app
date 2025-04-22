<script setup>

defineProps({
    tip: {
        type: Number,
        required: true,
        default: 0
    },
    isActive: {
        type: Boolean,
        required: true,
        default: false
    }
})
defineEmits(['update:modelValue'])


</script>
<template>
    <button :class="{enableButton: isActive  }" class="tip-button green-900 rounded-md text-preset-3" @click="$emit('update:modelValue', tip)" >{{ tip }}%</button>
</template>
<style scoped>
.tip-button {
    color: white;
    border: none;
    padding: .2em 1.5em;
    cursor: pointer;
    margin: 5px;
    
}
.enableButton {
    background-color: #26C2AE;
    color: #00474B;
}
.tip-button:hover {
    background-color: #9FE8DF;
}

</style>