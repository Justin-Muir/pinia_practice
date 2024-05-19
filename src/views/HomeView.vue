
<template>
  <div>
    <div>
     {{storeCounter.count}}
    </div>
    <div>
      <button @click="decreseCount">-</button>
      <h1> </h1>
      <button @click="increaseCount">+</button>
    </div>
    <hr>
    <div>
      This counter is: {{ oddOrEven }}
    </div>
  </div>
</template>
<script setup>
import {ref, computed} from 'vue'
import { useCounterStore} from '../stores/counter'

const storeCounter = useCounterStore()

const count = ref(0)

const increaseCount = () => {
  count.value++
}
const decreseCount = () => {
  count.value--
}

const oddOrEven = computed(() =>{
  if (count.value % 2 === 0) return 'even'
  return 'odd'
})
</script>