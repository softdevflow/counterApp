

<template>
  <q-page>
    <div class="flex flex-center">
      <h1 class="no-margin text-white  no-padding">About us</h1>
    </div>

    <div class="q-pa-md">
      <q-carousel
        v-model="slide"
        transition-prev="slide-right"
        transition-next="slide-left"
        swipeable
        animated
        control-color="amber"
        navigation
        padding
        arrows
        height="300px"
        class="bg-transparent rounded-borders"
      >
        <q-carousel-slide :name="1" class="column no-wrap">
          <div class="row fit justify-start items-center q-gutter-xs q-col-gutter no-wrap">
            <q-img class="rounded-borders col-6 full-height" src="https://cdn.quasar.dev/img/mountains.jpg" />
            <q-img class="rounded-borders col-6 full-height" src="https://cdn.quasar.dev/img/parallax1.jpg" />
          </div>
        </q-carousel-slide>
        <q-carousel-slide :name="2" class="column no-wrap">
          <div class="row fit justify-start items-center q-gutter-xs q-col-gutter no-wrap">
            <q-img class="rounded-borders col-6 full-height" src="https://cdn.quasar.dev/img/parallax2.jpg" />
            <q-img class="rounded-borders col-6 full-height" src="https://cdn.quasar.dev/img/quasar.jpg" />
          </div>
        </q-carousel-slide>
        <q-carousel-slide :name="3" class="column no-wrap">
          <div class="row fit justify-start items-center q-gutter-xs q-col-gutter no-wrap">
            <q-img class="rounded-borders col-6 full-height" src="https://cdn.quasar.dev/img/cat.jpg" />
            <q-img class="rounded-borders col-6 full-height" src="https://cdn.quasar.dev/img/linux-avatar.png" />
          </div>
        </q-carousel-slide>
        <q-carousel-slide :name="4" class="column no-wrap">
          <div class="row fit justify-start items-center q-gutter-xs q-col-gutter no-wrap">
            <q-img class="rounded-borders col-6 full-height" src="https://cdn.quasar.dev/img/material.png" />
            <q-img class="rounded-borders col-6 full-height" src="https://cdn.quasar.dev/img/donuts.png" />
          </div>
        </q-carousel-slide>
      </q-carousel>
    </div>

    <div class="flex flex-center q-ma-md">
      <q-btn color="green" rounded @click="$router.push('/')" label="MAIN PAGE" size="xl" />
    </div>


  </q-page>



</template>
<script>
import { ref } from 'vue'

export default {
  setup () {
    return {
      slide: ref(1)
    }
  }
}
</script>
<style scoped></style>
