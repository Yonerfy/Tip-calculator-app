<script setup>
defineProps({
    modelValue: {
        type: Number,
        required: true
    },
    onFocus: {
        type: Function,
        required: false
    }
})

const emit = defineEmits(['update:modelValue'])
function onInput(event) {
    const value = Number(event.target.value)
    if (value >= 0) {
        emit('update:modelValue', value)
    } else {
        event.target.value = 0 // Reset the input field to 0 if the user enters a negative value
        emit('update:modelValue', 0)
    }
}
</script>
<template>
    <div class="input-form mb-[3em] md:mb-0">
        <label for="bill" class="text-preset-5 text-left text-[#5E7A7D]">Bill</label>
        <div class="bill-container flex items-center relative mt-2">
            <img src="../assets/icon-dollar.svg" alt="Dollar icon" class="icon-dollar" />
            <input :value="modelValue" @focus="onFocus" @input="onInput" type="number" id="bill" placeholder="0" class="w-[23.688em] text-right bg-[#F3F9FA] p-[.5em] rounded-md text-[#00474B]
            text-preset-3"  />
        </div>
        
    </div>
</template>
<style scoped>
.icon-dollar {
    position: absolute;
    left: 4%;
}

</style>