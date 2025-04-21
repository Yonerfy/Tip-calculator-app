<script setup></script>
<template>
    <div class="input-form">
        <label for="bill" class="text-preset-5 text-left text-[#5E7A7D]">Bill</label>
        <div class="bill-container flex items-center relative mt-2">
            <img src="../assets/icon-dollar.svg" alt="Dollar icon" class="icon-dollar" />
            <input type="number" id="bill" placeholder="0" class="w-[23.688em] text-right bg-[#F3F9FA] p-[.5em] rounded-md text-[#00474B]
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