<template>
  <div>
    <div>
      <div class="black-bg" v-if="모달창열렸니 == true">
        <div class="white-bg">
          <h4>상세페이지</h4>
          <p>상세페이지내용임</p>
          <button @click="모달창열렸니 = false">닫기</button>
        </div>
      </div>
    </div>

    <div class="menu">
      <a v-for="작명 in 메뉴들" :key="작명">{{ 작명 }}</a>
    </div>

    <div>
      <img alt="Vue logo" src="./assets/logo.png" />
      <div v-for="(a, i) in products" :key="i">
        <img :src="products[i].image" class="room-img" />
        <h4 @click="모달창열렸니 = true">{{ products[i].title }}</h4>
        <p>{{ products[i].price }} 원</p>
        <!-- <button @click="신고수[i]++">허위매물신고</button>
        <span>신고수 : {{ 신고수[i] }}</span> -->
      </div>
    </div>
  </div>
</template>

<script>
import data from "./assets/oneroom.js";

export default {
  name: "App",
  data() {
    return {
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

  components: {},
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
