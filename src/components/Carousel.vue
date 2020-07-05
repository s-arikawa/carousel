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
import Vue, { PropType } from "vue";

export type DataType = {
  index: number;
};

export default Vue.extend({
  props: {
    itemList: {
      type: Array as PropType<string[]>,
      required: true
    }
  },

  data(): DataType {
    return {
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
