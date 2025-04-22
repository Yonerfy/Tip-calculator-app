<script setup>
defineProps({
    tipAmount: {
        type: Number,
        required: true,
        default: 0
    },
    totalAmount: {
        type: Number,
        required: true,
        default: 0
    },
})
defineEmits(['reset'])
</script>
<template>
    <div class="tip-card bg-[#00474B] rounded-xl p-[2em] ">
        <div class="tip-amound-container flex justify-between mt-5">
            <div class="tipLetter">
                <h2 class="text-preset-5 text-white">Tip amount</h2>
                <span class="text-preset-6 text-[#7F9D9F]">/ person</span>
            </div>
            <div class="text-preset-1 text-[#26C2AE]">${{ tipAmount.toFixed(2) }}</div>
        </div>
        <div class="total-person-container flex justify-between mt-[2em]">
            <div class="tipLetters">
                <h2 class="text-preset-5 text-white">Total</h2>
                <span class="text-preset-6 text-[#7F9D9F]">/ person</span>
            </div>
            <div class="text-preset-1 text-[#26C2AE]">${{ totalAmount.toFixed(2) }}</div>
        </div>
        <div class="button-container flex justify-center mt-[8em]">
            <button class="green-750 rounded-md text-preset-4 text-[#085C61] p-[.5em] w-[23.688em]" 
                @click="$emit('reset')" :disabled="tipAmount === 0" :class="{enableButton: tipAmount > 0}">Reset
            </button>
        </div>
    </div>
</template>
<style scoped>
.enableButton {
    background-color: #26C2AE;
    color: #00474B;
}
.enableButton:hover {
    background-color: #9FE8DF;
}
</style> 
