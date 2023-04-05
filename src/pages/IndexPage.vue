<template>
  <q-page padding>
    <input
    v-model="message"
    @keyup.esc="clearMessage"
    @keyup.enter="alertMessage"
    />
    <button @click="clearMessage">Clear</button>
    <h5>{{ message }}</h5>
  </q-page>
</template>

<script>
export default {
  data() {
    return {
      message: "in to the game",
      errorMessage: "yapacağın işi s2m"
    }
  },
  methods: {
    clearMessage() {
      this.message = ''
    },
    alertMessage() {
      alert(this.errorMessage)
    }
  },
}
</script>
