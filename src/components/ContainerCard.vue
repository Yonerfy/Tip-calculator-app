<script setup>
import TipButton from './TipButton.vue'
import InputFormBill from './InputFormBill.vue'
import TipCard from './TipCard.vue'
import InputFormPeople from './InputFormPeople.vue'
import InputCustomTip from './InputCustomTip.vue'
</script>

<template>
  <div class="logo-container md:mb-[2em] lg:mb-[5.438em] flex justify-center">
    <img src="../assets/logo.svg" alt="Logo" class="logo" />
  </div>

 <div class="white-bg bg-white p-7 rounded-xl shadow-lg">
  <div class="card p-[1em]">
    <div class="card-left">
      <InputFormBill  />
      <h2 class="text-preset-5 text-left text-[#5E7A7D] mt-[2.5em] mb-2">Select Tip %</h2>
      <div class="tips-container flex flex-wrap gap-1">
        <TipButton :tip="5" />
        <TipButton :tip="10"/>
        <TipButton :tip="15"/>
        <TipButton :tip="25"/>
        <TipButton :tip="50"/>
        <InputCustomTip :tip="Custom"/>
      </div>
      <InputFormPeople />
    </div>
    <div class="card-right">
      <TipCard />
    </div>
  </div>
 </div>

</template>

<style scoped>
.card{
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: auto;
  gap: 2em;
  grid-template-areas: 
    "left right";
}

.card-left{
  grid-area: left;
}
.card-right{
  grid-area: right;
}

@media (max-width: 768px) {
  .card {
    grid-template-columns: 1fr;
    grid-template-areas: 
      "left"
      "right";
  }
}
</style>
