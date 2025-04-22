<script setup>
import TipButton from './TipButton.vue'
import InputFormBill from './InputFormBill.vue'
import TipCard from './TipCard.vue'
import InputFormPeople from './InputFormPeople.vue'
import InputCustomTip from './InputCustomTip.vue'
import { ref,computed } from 'vue'
const bill = ref(0)
const people = ref(1)
const selectedTip = ref(0)
const isButtonActive = (tip) => {
    return selectedTip.value === tip
}
// Calculate the tip amount
const tipAmount = computed(() => {
    if (people.value > 0) {
        return (bill.value * selectedTip.value) / 100 
    }
    return 0
})
// Calculate the total amount
const totalAmount = computed(() => {
    if (tipAmount.value > 0 && people.value > 0) {
        return tipAmount.value / people.value
    }
    return 0
})
// Reset the values
const resetValues = () => {
    bill.value = 0
    people.value = 1
    selectedTip.value = 0
}
</script>

<template>
  <div class="logo-container my-[5em] md:mt-[0] md:mb-[2em] lg:mb-[5.438em] flex justify-center">
    <img src="../assets/logo.svg" alt="Logo" class="logo" />
  </div>

 <div class="white-bg bg-white p-7 rounded-xl shadow-lg">
  <div class="card py-[3em] md:p-[1em]">
    <div class="card-left">
      <InputFormBill  v-model="bill"/>
      <h2 class="text-preset-5 text-left text-[#5E7A7D] mt-[2.5em] mb-2">Select Tip %</h2>
      <div class="tips-container flex flex-wrap gap-1">
        <TipButton v-for="tip in [5, 10, 15, 25, 50]" :key="tip" :totalAmount="totalAmount" :tip="tip" v-model="selectedTip" :isActive="isButtonActive(tip)" />
        <InputCustomTip v-model="selectedTip" :tip="selectedTip"/>
      </div>
      <InputFormPeople v-model="people"/>
    </div>
    <div class="card-right">
      <TipCard :tipAmount="tipAmount" :totalAmount="totalAmount" @reset="resetValues"/>
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
@media(max-width: 426px ) {
  /* .white-bg{
    height: 131vh;
  } */
}
</style>
