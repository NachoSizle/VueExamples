<template>
  <h2 v-html="myName"></h2>
  <button @click="state.count++" :class="`btn-${getButtonClass()}`">
    {{ `Count is: ${state.count}` }}
  </button>
  <button v-for="elem in elements" :key="`elem-${elem.btnText}`" @click.prevent="elem.fn">
    {{ elem.btnText }}
  </button>
</template>

<script setup>
import { ref, reactive } from 'vue'

const myName = ref('Completed on <span>Jun 22, 23</span>')

const state = reactive({
  count: 0
})

const increaseCount = () => {
  state.count++
}

const changeName = () => {
  myName.value = 'Jul 23, 23'
}

const elements = reactive([
  {
    btnText: 'Change name',
    fn: changeName
  },
  {
    btnText: 'Increase count',
    fn: increaseCount
  },
])

const getButtonClass = () => {
  if (state.count === 1) {
    return 'warning';
  }

  if (state.count === 2) {
    return 'danger';
  }

  if (state.count === 3) {
    return 'success';
  }

  return 'normal';
}

console.log(myName)
</script>

<style>
.btn-danger {
  background-color: red;
}

.btn-warning {
  background-color: yellow;
}

.btn-success {
  background-color: green;
}
</style>