<script setup>
defineProps({
    tip: {
        type: Number,
        required: true
    }
})

</script>
<template>
    <button class="tip-button green-900 rounded-md text-preset-3" >{{ tip }}%</button>
</template>
<style scoped>
.tip-button {
    color: white;
    border: none;
    padding: .2em 1.5em;
    cursor: pointer;
    margin: 5px;
    
}

</style>