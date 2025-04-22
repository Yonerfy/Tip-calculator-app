<script setup>
defineProps(['modelValue'])
defineEmits(['update:modelValue'])
</script>
<template>
    <div class="input-form mb-[3em] md:mb-0">
        <label for="bill" class="text-preset-5 text-left text-[#5E7A7D]">Bill</label>
        <div class="bill-container flex items-center relative mt-2">
            <img src="../assets/icon-dollar.svg" alt="Dollar icon" class="icon-dollar" />
            <input :value="modelValue" @input="$emit('update:modelValue', $event.target.value)" type="number" id="bill" placeholder="0" class="w-[23.688em] text-right bg-[#F3F9FA] p-[.5em] rounded-md text-[#00474B]
            text-preset-3"  />
        </div>
        
    </div>
</template>
<style scoped>
.icon-dollar {
    position: absolute;
    left: 4%;
}
/* @media(max-width: 426px ) {
  .white-bg{
    height: 131vh;
  }
} */
</style>