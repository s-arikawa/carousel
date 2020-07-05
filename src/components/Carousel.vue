<template>
  <div class="carousel">
    <div class="itemList" :style="itemListStyle">
      <div v-for="(item, i) in itemList" :key="i" class="item">
        <img :src="item" class="img" alt="" width="300" height="300"/>
      </div>
    </div>
    <div class="control">
      <button @click="moveIndex(-1)">← 前へ</button>
      <button @click="moveIndex(1)">→ 次へ</button>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export type DataType = {
  itemList: string[];
  index: number;
};

export default Vue.extend({
  data(): DataType {
    return {
      itemList: [
        "https://4.bp.blogspot.com/-w24eW1baFyk/W-VEb7li4DI/AAAAAAABQFY/xyV3enhHatcL6oXF0_BlOVwRdvHyK6feACLcBGAs/s800/dog_pomeranian.png",
        "https://4.bp.blogspot.com/-jDG-EHpiWDQ/Ur1HdybdzMI/AAAAAAAAcg8/KwaSvHiDAdw/s400/dog_rottweiler.png",
        "https://1.bp.blogspot.com/-tnYqrXJ3pfU/Ur1HcKFGnjI/AAAAAAAAcgk/Dqob5GlfMg4/s800/dog_papillon.png",
        "https://3.bp.blogspot.com/-qV9Nbph35jE/Ur1HYs1iZ2I/AAAAAAAAcfY/Hait5vnT20k/s800/dog_doberman.png",
        "https://4.bp.blogspot.com/-4tq-__D2zTw/Ur1HT115bAI/AAAAAAAAceI/2b2_0tft5kw/s800/dog_boxer.png"
      ],
      index: 0
    };
  },
  computed: {
    itemListStyle(): Record<string, string> {
      return {
        transform: `translateX(${this.index * -100}%)`
      };
    }
  },
  methods: {
    moveIndex(diff: number): void {
      const index = (this.index + diff) % this.itemList.length;
      this.index = index < 0 ? index + this.itemList.length : index;
    }
  }
});
</script>

<style lang="scss" scoped>
.carousel {
  width: 300px;
  overflow: hidden;

  .itemList {
    display: flex;
    transition: ease 0.2s;
  }

  .item {
  }

  .img {
  }
}

.control {
}
</style>
