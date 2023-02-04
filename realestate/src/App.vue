<template>

  <div class="black-bg" v-if="open_modal">
    <div class="white-bg">
      <button @click="open_modal = false" class="close-button">닫기</button>
      
      <h4>상세페이지</h4>
      <p>상세페이지 내용</p>
    </div>
  </div>

  <div class="menu">
    <a v-for="menu in menus" :key="menu">{{ menu }}</a>
  </div>
  <!-- <div v-for="(product, i) in products" :key="i">
    <img :src='`@/assets/room${i}.jpg`' class="room-img">
    <h4>{{ product }}</h4>
    <p>{{ i }}</p>
    <p>{{ price[i] }} 만원</p>
    <button @click="report_count[i]++">허위매물신고</button> <span>신고수 : {{ report_count[i] }}</span>
  </div> -->
  <div>
    <img src='./assets/room0.jpg' class="room-img">
    <h4 @click="open_modal = true">{{ products[0] }}</h4>
    <p>{{ price[0] }} 만원</p>
    <button @click="report_count[0]++">허위매물신고</button> <span>신고수 : {{ report_count[0] }}</span>
  </div>
  <div>
    <img src='./assets/room1.jpg' class="room-img">
    <h4>{{ products[1] }}</h4>
    <p>{{ price[1] }} 만원</p>
    <button @click="report_count[1]++">허위매물신고</button> <span>신고수 : {{ report_count[1] }}</span>
  </div>
  <div>
    <img src='./assets/room2.jpg' class="room-img">
    <h4>{{ products[2] }}</h4>
    <p>{{ price[2] }} 만원</p>
    <button @click="report_count[2]++">허위매물신고</button> <span>신고수 : {{ report_count[2] }}</span>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      open_modal: false,
      report_count: [0, 0, 0],
      products: ['역삼동원룸', '삼성동원룸', '논현동원룸'],
      price: [50, 100, 150],
      menus: ['Home', 'Products', 'About']
    }
  },
  methods: {

  },
  components: {
    
  }
}
</script>

<style>
body {
  margin: 0;
}
div {
  box-sizing: border-box;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.room-img {
  width: 100%;
  margin-top: 40px;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a{
  color: white;
  padding: 10px;
}

.black-bg {
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  width: 100%;
  background: white;
  padding: 20px;
  border-radius: 8px;
}
.close-button{
  float: right;
  background: darkslateblue;
  color: white;
  border: none;
  border-radius: 5px;
  padding: 5px 10px;
}
</style>
