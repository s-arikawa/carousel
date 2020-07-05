<template>
  <div id="app">
    <Carousel :item-list="itemList" />
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import Carousel from "@/components/Carousel.vue";

const itemList = [
  "https://4.bp.blogspot.com/-w24eW1baFyk/W-VEb7li4DI/AAAAAAABQFY/xyV3enhHatcL6oXF0_BlOVwRdvHyK6feACLcBGAs/s800/dog_pomeranian.png",
  "https://4.bp.blogspot.com/-jDG-EHpiWDQ/Ur1HdybdzMI/AAAAAAAAcg8/KwaSvHiDAdw/s400/dog_rottweiler.png",
  "https://1.bp.blogspot.com/-tnYqrXJ3pfU/Ur1HcKFGnjI/AAAAAAAAcgk/Dqob5GlfMg4/s800/dog_papillon.png",
  "https://3.bp.blogspot.com/-qV9Nbph35jE/Ur1HYs1iZ2I/AAAAAAAAcfY/Hait5vnT20k/s800/dog_doberman.png",
  "https://4.bp.blogspot.com/-4tq-__D2zTw/Ur1HT115bAI/AAAAAAAAceI/2b2_0tft5kw/s800/dog_boxer.png"
];

export default Vue.extend({
  name: "App",
  components: {
    Carousel
  },
  data() {
    return {
      itemList
    };
  }
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
