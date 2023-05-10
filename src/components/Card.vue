<template>
  <div>
    <img :src="원룸.image" class="room-img">
    <h4 v-on:click="$emit('openModal', 원룸.id)">{{ 원룸.title }}</h4>
    <p>{{ 원룸.content }}</p>
    <p>{{ 원룸.price }}</p>
  </div>
</template>

<script>
export default {
    name:'CardThing',
    props:{
        원룸:Object,
        누른거:Number,
        모달창:Boolean,
    }
}
</script>

<style>
    .room-img{
    width: 100%;
    margin-top: 40px;
    }
</style>