<template>
    <div class="black-bg" v-if="모달창 == true">
    <div class="white-bg">
      <h4>{{ 원룸들[누른거].title }}</h4>
      <p>{{ 원룸들[누른거].content }}</p>
      <!-- <button v-on:click="모달창=false">모달창닫아</button> -->
    </div>
  </div>
</template>

<script>
export default {
    name:'ModalPage',
    props:{
        원룸들:Array,
        누른거:Number,
        모달창:Boolean,
    }
}
</script>

<style>
    .black-bg {
        width: 100%; height: 100%;
        background: rgba(0,0,0,0.5);
        position: fixed; padding: 20px;
    }
    .white-bg {
        width: 100%; background: white;
        border-radius: 8px;
        padding: 20px;
    }
</style>