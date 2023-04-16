<template>
  <q-page padding>
    <input
    v-model="message"
    @keyup.esc="clearMessage"
    @keyup.enter="alertMessage"/>

    <button @click="clearMessage">Clear</button>

    <h5
      v-if="message.length"
      class="border-grey">{{ message }}</h5>
      <h6 v-else>No message entered...</h6>

    <!-- v-if kullanımı; NOT: farkları, v-if elementi tamamen domdan kaldırır ve v-else alternatifini kullanmamızı sağlar. Yani kullanım yanlışsa alternatif üretebiliriz.
      Yukarıda v-else örneği verdik, mesaj uzunluğu belirttiğimiz gibi değil ise (false) No message entered yazacak. Yani mesaj girilirse ve mesajıun lengthine ulaşılırsa box içeriisne yazdırıyoruz. ancak boş ise yani if dışında başka bir ihtimal olur ise else bastırıyoruz.
        <h5
      v-if="message.length"
      class="border-grey">{{ message }}</h5> -->

    <!-- v-show kullanımı;(alternatifi v-if)
      <h5 class="border-grey" v-show="message.length">{{ message }}</h5> -->
    <!-- v-show: Bir elementin görünürlüğünü kontrol eder. Burada yaptığımız şey, "mesajın uzunluğu bizim atadığımız mesaj kadar oluras yani '' sıfır olursa mesaj kutusunu gösterme"
    demek oluyor. h5 içerisindeki yerde tanımladığımız için orayı görünür/görünmez kılar. Ve bunu CSS kullanarak yapar(inspect edip kaybolan yere baktığımızda style kısmına display verdiğini görürüz. style="display")-->
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
        alert(this.message)
      }
    },
  }
</script>

<style>
  .border-grey {
    border: 1px solid grey;
  }
</style>
