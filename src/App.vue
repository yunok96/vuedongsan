<template>

  <modal-page @closeModal="모달창 = false"
  v-bind:원룸들="원룸들"
  v-bind:누른거="누른거"
  v-bind:모달창="모달창"
  />

  <div class="menu">
    <a v-for="a in menus" :key="a">{{ a }}</a>
  </div>

  <dis-ban/>

  <card-thing @openModal="모달창 = true; 누른거 = $event" v-for="(a,i) in 원룸들" :key="i"
  v-bind:원룸="원룸들[i]"
  v-bind:모달창="모달창"
  v-bind:누른거="누른거"
  />

</template>

<script>
import data from './assets/data.js';
import DiscountBanner from './components/DiscountBanner.vue';
import Modal from './components/Modal.vue';
import CardThing from './components/Card.vue'

export default {
  name: 'App',
  data(){
    return {
      누른거:0,
      원룸들:data,
      모달창: false,
      신고수 : 0,
      menus: ['Home', 'Products', 'About'],
      products: ['역삼동원룸', '천호동원룸', '강남동원룸']
    }
  },
  methods : {
    어쩌구() {
      this.신고수 += 1;
    },
  },
  components: {
    DisBan : DiscountBanner,
    ModalPage : Modal,
    CardThing : CardThing,
  }
}

</script>

<style>
body {
  margin: 0;
}
div {
  box-sizing: border-box;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background-color: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}

</style>
