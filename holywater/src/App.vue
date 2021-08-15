<template>
<div class="black-bg" v-if="모달오픈 == true">
  <div class="white-bg">
    <h4>상세페이지</h4>
    <p>상세페이지 내용</p>
    <button @click="모달오픈 = false">닫기</button>
  </div>
</div>

  <div class="menu">

    <a v-for="About in 메뉴들" :key="About"> {{ About }}</a>

  </div>
  <h1 :style="green">부동산</h1>
  <div>
    <img src="./assets/room0.jpg" class="room-img">
    <h4 @click="모달오픈 = true">{{ products[0] }} 원룸</h4>
    <p>{{price[0]}}만원</p>
    <button @click="increase0">허위매물 신고</button> 
    <sapn> 신고 수 : {{ 신고수[0] }}</sapn>
  </div>
  <div>
    <img src="./assets/room1.jpg" class="room-img">
    <h4>{{ products[1] }} 원룸</h4>
    <p>{{price[1]}}만원</p>
    <button @click="increase1">허위매물 신고</button> 
    <sapn> 신고 수 : {{ 신고수[1] }}</sapn>
  </div>
  <div>
    <img src="./assets/room2.jpg" class="room-img">
    <h4>{{ products[2] }} 원룸</h4>
    <p>{{price[2]}}만원</p>
    <button @click="increase2">허위매물 신고</button> 
    <sapn> 신고 수 : {{ 신고수[2] }}</sapn>
  </div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return{
      모달오픈 : false,
      price : ['50', '60', '55'],
      green : 'color : green',
      products : ['역삼동', '천호동', '마포구'],
      메뉴들 : ['Home', 'Products', 'About'],
      신고수 : [0,0,0] 
    }
  },
  methods : {
    increase0(){
      this.신고수[0] += 1;
    },
    increase1(){
      this.신고수[1] += 1;
    },
    increase2(){
      this.신고수[2] += 1;
    }
  },
  components: {
    
  }
}
</script>

<style>
body {
  margin: 0
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}
</style>

<style>
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
  color: white;
  padding: 10px;
}
.room-img {
  width: 70%;
  margin-top: 40px;
}
</style>
