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
        event.target.value = 1 // Reset the input field to 0 if the user enters a negative value
        emit('update:modelValue', 1)
    }
}
</script>
<template>
    <div class="input-form mt-[2.5em] mb-[3em] md:mb-0">
        <div class="label-container flex justify-between">
            <label for="people" class="text-preset-5 text-left text-[#5E7A7D] mb-2">Number of people</label>
            <span v-if="modelValue <=0" class="text-[#E17052]">Can’t be zero</span>
        </div>
        <div class="people-container flex items-center relative mt-2">
            <img src="../assets/icon-person.svg" alt="People icon" class="icon-dollar" />
            <input :class="{errormessage:modelValue == 0}" :value="modelValue" @focus="onFocus" @input="onInput" type="number" id="people" placeholder="0" class="w-[23.688em] text-right bg-[#F3F9FA] p-[.5em] rounded-md text-[#00474B]
            text-preset-3"  />
        </div> 
    </div>
</template>
<style scoped>
.icon-dollar {
    position: absolute;
    left: 4%;
}
.errormessage, .errormessage:focus-visible{
    border-color: #E17052;
    border: 2px solid #E17052;
}
</style>