<template>
  <div>
    <div class="menu">
      <a v-for="작명 in 메뉴들" :key="작명">{{ 작명 }}</a>
    </div>

    <div>
      <img alt="Vue logo" src="./assets/logo.png" />
      <div v-for="(a, i) in products" :key="i">
        <h4>{{ products[i] }}</h4>
        <p>{{ price1 }}만원</p>
        <button @click="신고수++">허위매물신고</button>
        <span>신고수 : {{ 신고수 }}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      신고수: 0,
      price1: 70,
      메뉴들: ["Home", "Shop", "About"],
      products: ["원룸1", "투룸"],
    };
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
</style>
