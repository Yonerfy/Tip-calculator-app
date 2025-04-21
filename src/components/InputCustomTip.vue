<script setup>

defineProps({
    tip: {
        type: Number,
        required: true
    }
})

</script>
<template>
    <input type="number" class="custom-button bg-[#F3F9FA] rounded-md text-[#00474B] text-preset-3 text-right w-[31%]"  placeholder="Custom"/>
</template>
<style scoped>
.custom-button {
    border: none;
    cursor: pointer;
    padding: .2em 1.5em;
}
</style>