<template>
  <div class="counter-container">
    <h2 v-if="state.count === 4" v-html="myName"></h2>

    <h2 v-if="state.count === 2">Im Fede</h2>
    <h2 v-else-if="state.count === 3">Im Adrian</h2>
    <h2 v-else>Im Nacho!</h2>
    <button @click="state.count++" :class="`btn-${getButtonClass()}`">
      {{ `Count is: ${state.count}` }}
    </button>


    <button 
      v-for="elem in elements" 
      :key="`elem-${elem.btnText}`"
      @click.prevent="elem.fn">
      {{ elem.btnText }}
    </button>
  </div>
</template>

<script>
export default {
  name: 'CounterComp',
  data() {
    return {
      elements: [
        {
          btnText: 'Change name',
          fn: this.changeName
        },
        {
          btnText: 'Increase count',
          fn: this.increaseCount
        },
      ],
      buttonClass: 'danger',
      myName: 'Completed on <span>Jun 22, 23</span>',
      state: {
        count: 1,
      }
    }
  },
  methods: {
    increaseCount() {
      this.state.count++;
    },
    changeName() {
      this.myName = 'Jul 23, 23';
    },
    getButtonClass() {
      if (this.state.count === 1) {
        return 'warning';
      }

      if (this.state.count === 2) {
        return 'danger';
      }

      if (this.state.count === 3) {
        return 'success';
      }

      return 'normal';
    }
  },
  unmounted() {

  },
  created() {
    console.log('CounterComp --> Created')
  }
}
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
.counter-container button {
  background-color: aqua;
}
</style>