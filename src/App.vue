<template>
  <div class="black-bg" v-if="modalOpen">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>상세 내용</p>
      <button @click="modalOpen = false">닫기</button>
    </div>
  </div>
  <div class="menu">
    <a v-for="elements in menu" :key="elements">{{ elements }}</a>
  </div>
  <!-- <div v-for="(product, i) in products" :key="i"> -->
  <!-- <h4>{{ product }}</h4> -->
  <!-- <h4>{{ products[i] }}</h4> -->
  <!-- <p>만원</p> -->
  <!-- </div> -->
  <div>
    <img src="./assets/nian.png" class="room-img" />
    <h4 @click="modalOpen = true">{{ products[0] }}</h4>
    <p>50</p>
    <button @click="declaration[0]++">허위매물 신고</button>
    <span>신고 수 : {{ declaration[0] }}</span>
  </div>
  <div>
    <img src="./assets/el.png" class="room-img" />
    <h4>{{ products[1] }}</h4>
    <p>80</p>
    <button @click="declaration[1]++">허위매물 신고</button>
    <span>신고 수 : {{ declaration[1] }}</span>
  </div>
  <div>
    <img src="./assets/ell.png" class="room-img" />
    <h4>{{ products[2] }}</h4>
    <p>90</p>
    <button @click="declaration[2]++">허위매물 신고</button>
    <span>신고 수 : {{ declaration[2] }}</span>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      menu: ["Home", "Shop", "About"],
      products: ["역삼동", "논현동", "잠원동"],
      declaration: [0, 0, 0],
      // ui(모달) 상태 저장
      modalOpen: false,
    };
  },
  methods: {
    increase() {
      this.declaration++;
    },
  },
  components: {},
};
</script>

<style>
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
  background: #fff;
  border-radius: 8px;
  padding: 20px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: #fff;
  padding: 10px;
}
.room-img {
  width: 100%;
  margin-top: 40px;
}
</style>
