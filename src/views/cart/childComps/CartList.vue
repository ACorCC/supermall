<template>
  <div class="cart-list">
    <scroll class="content">
      <li v-for="(item, index) in cartList" :key="index">
        <cart-list-item :item-info="item"></cart-list-item>
      </li>
    </scroll>
  </div>
</template>

<script>
import Scroll from "components/common/scroll/Scroll";

import CartListItem from "./CartListItem.vue";

import { mapGetters } from "vuex";

export default {
  components: {
    Scroll,
    CartListItem,
  },
  computed: {
    ...mapGetters(["cartList"]),
  },
};
</script>

<style scoped>
li {
  list-style: none;
}
.cart-list {
  height: calc(100vh - 44px - 49px);
}
.content {
  height: 100%;
  overflow: hidden;
}
</style>
