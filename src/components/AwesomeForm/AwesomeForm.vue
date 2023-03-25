<template>
  <section class="form--container">
  <h1>My name is: {{ formData.name }}</h1>
  <form>
    <label for="name">Name:</label>
    <input type="text" name="name" v-model="formData.name" placeholder="Introduce tu nombre" />

    <label for="surname">Surname:</label>
    <input type="text" name="surname" v-model="formData.surname" placeholder="Introduce tu apellido" />
    <label for="age">Age:</label>
    <input type="number" name="age" v-model="formData.age" placeholder="Introduce tu edad" />

    <input type="checkbox" name="place" v-model="formData.place.isMadrilenio" />
    <label for="place">Madrileño?</label>

    <label for="place" v-if="isVIPUser">
      <input type="checkbox" name="place" v-model="formData.place.isCatalan" />
      Catalán?
    </label>

    <div v-if="isVIPUser" class="form__vipData">
      <input type="radio" id="one" value="One" v-model="formData.picked" />
      <label for="one">One</label>

      <input type="radio" id="two" value="Two" v-model="formData.picked" />
      <label for="two">Two</label>

      <button type="button" @click.prevent="_validateAndUpdateContact">Send</button>

      <div>Selected: {{ formData.selected }}</div>

      <select v-model="formData.selected">
        <option disabled value="">Please select one</option>
        <option>A</option>
        <option>B</option>
        <option>C</option>
      </select>
    </div>
  </form>
  <button @click="_changeUserType">Change User</button>
</section>
</template>
  

<script>
export default {
  name: 'AwesomeForm',
  data() {
    return {
      isVIPUser: false,
      formData: {
        name: '',
        surname: '',
        age: 29,
        place: {
          isMadrilenio: false,
          isCatalan: false
        },
        picked: 'One',
        selected: ''
      }
    }
  },
  methods: {
    _validateForm() {
      console.log('Validating form...')
      console.log(this.formData)
    },
    _validateAndUpdateContact() {
      this._validateForm()
      this._updateContact()
    },
    _updateContact() {
      fetch('asdjkhgashkjgdashd', {
        method: 'POST',
        body: this.formData
      })
    },
    _changeUserType() {
      this.isVIPUser = !this.isVIPUser;
    }
  }
}
</script>

<style scoped>
</style>