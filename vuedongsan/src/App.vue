<template>
  <div>
    <Modal :products="products" :누른거="누른거" :모달창열렸니="모달창열렸니" />

    <div class="menu">
      <a v-for="작명 in 메뉴들" :key="작명">{{ 작명 }}</a>
    </div>

    <Discount v-bind="오브젝트" />

    <!-- props 나머지 내용 조금 & 저번 시간 숙제까지 수강함-->
    <Card :product="products[i]" v-for="(작명, i) in products" :key="작명" />
  </div>
</template>

<script>
import data from "./assets/oneroom.js";
import Discount from "./Discount.vue";
import Modal from "./Modal.vue";
import Card from "./Card.vue";

export default {
  name: "App",
  data() {
    return {
      오브젝트: { name: "kim", age: 20 },
      누른거: 0,
      모달창열렸니: false,
      // 신고수: [0, 0, 0],
      // price1: 70,
      메뉴들: ["Home", "Shop", "About"],
      products: data,
    };
  },

  methods: {
    increase() {
      this.신고수++;
    },
  },

  components: {
    Discount: Discount,
    Modal: Modal,
    Card: Card,
  },
};
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

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}

body {
  margin: 0;
}
div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}
.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
</style>
