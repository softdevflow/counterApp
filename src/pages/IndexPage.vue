<template>
  <q-page v-touch-pan.vertical.prevent.mouse="handlePan" class="flex flex-center text-white">
    <div class="row">
      <q-input
        v-model="data.name"
        input-class="text-center text-h5 text-white"
        color="pink"
        placeholder="Counter"
        filled
      />
    </div>
    <div class="row full-width items-center">
      <div class="col text-center">
        <q-btn
          @click="decreaseCounter"
          v-touch-repeat:300:300:300:300:50.mouse="decreaseCounter"
          icon="remove"
          size="xl"
          round
        />
      </div>
      <div class="col text-center text-h2">{{ data.counter }}</div>
      <div class="col text-center">
        <q-btn
          @click="increaseCounter"
          v-touch-repeat:300:300:300:300:50.mouse="increaseCounter"
          icon="add"
          size="xl"
          round
        />
      </div>
    </div>
    <div class="row">
      <q-btn class="q-ma-md" round @click="resetCounter" icon="restart_alt" size="xl" />
      <q-btn class="q-ma-md" color="red" rounded @click="$router.push('/test')" label="test" size="xl" />
      <q-btn class="q-ma-md" color="green" rounded @click="$router.push('/about')" label="About us" size="xl" />
    </div>
  </q-page>
</template>

<style scoped>
.q-page {
  max-width: 700px;
  margin: 0 auto;
}
</style>
<script setup>
// imports

import { reactive, watch } from 'vue'
import { useQuasar } from 'quasar'

// quasar

const $q = useQuasar()

// data

const data = reactive({
  counter: 0,
  name: '',
})

const savedData = $q.localStorage.getItem('data')
if (savedData) Object.assign(data, savedData)
watch(data, (value) => {
  $q.localStorage.set('data', value)
})

// counter methods

const increaseCounter = () => {
  data.counter++
}
const decreaseCounter = () => {
  if (data.counter > 0) data.counter--
}
const resetCounter = () => {
  data.counter = 0
}

// touch-pan

const handlePan = (e) => {
  console.log(e.delta.y)
  if (e.delta.y < 0) increaseCounter()
  else decreaseCounter()
}
</script>
