<template>
  <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <img :src="products[누른거].image" class="room-img" />
      <h4>{{ products[누른거].title }}</h4>
      <p>{{ products[누른거].content }}</p>
      <p>{{ products[누른거].price }}</p>
      <!-- <button @click="모달창열렸니 = false">닫기</button> -->
    </div>
  </div>
</template>

<script>
export default {
  name: "Modal",
  props: {
    products: Array,
    누른거: Number,
    모달창열렸니: Boolean,
  },
};
</script>

<style></style>
