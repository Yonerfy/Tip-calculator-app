<script setup></script>
<template>
    <div class="input-form mt-[2.5em]">
        <label for="people" class="text-preset-5 text-left text-[#5E7A7D] mb-2">Number of people</label>
        <div class="people-container flex items-center relative mt-2">
            <img src="../assets/icon-person.svg" alt="People icon" class="icon-dollar" />
            <input type="number" id="people" placeholder="0" class="w-[23.688em] text-right bg-[#F3F9FA] p-[.5em] rounded-md text-[#00474B]
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