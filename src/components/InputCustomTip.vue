<script setup>
import { watch, ref } from 'vue';

const props = defineProps({
    tip: {
        type: Number,
        required: true,
        default: 0
    },
    onFocus: {
        type: Function,
        required: false
    }
})
defineEmits(['update:modelValue'])
const inputValue = ref(0) // Initialize with the value of the `tip` prop

// Watch for changes in the `tip` prop and update the input value
watch(() => props.tip,
    (newTip) => {
        inputValue.value = newTip === 0 ? null : newTip
    },
    { immediate: true } // Ensure the watcher runs immediately to sync the initial value
)


</script>
<template>
    <input type="number" class="custom-button bg-[#F3F9FA] rounded-md text-[#00474B] text-preset-3 text-right w-[31%]"  
    placeholder="Custom" :value="inputValue" @focus="onFocus"  @input="$emit('update:modelValue', Number($event.target.value))" />
</template>
<style scoped>
.custom-button {
    border: none;
    cursor: pointer;
    padding: .2em 1.5em;
}
</style>