<template>
  <div>
    <div>
      <img :src="product.image" class="room-img" />
      <h4>
        {{ product.title }}
      </h4>
      <p>{{ product.price }} 원</p>
      <!-- <button @click="신고수[i]++">허위매물신고</button>
        <span>신고수 : {{ 신고수[i] }}</span> -->
    </div>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: {
    product: Object,
  },
};
</script>

<style></style>
