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
    <img :src="원룸[0].image" class="room-img">
    <h4 @click="모달오픈 = true">{{ 원룸[0].title }} 원룸</h4>
    <p>{{원룸[0].price}}원</p>
  </div>
  <div>
    <img :src="원룸[1].image" class="room-img">
    <h4>{{ 원룸[1].title }} 원룸</h4>
    <p>{{원룸[1].price}}원</p>
  </div>
  <div>
    <img :src="원룸[2].image" class="room-img">
    <h4>{{ 원룸[2].title }} 원룸</h4>
    <p>{{원룸[2].price}}원</p>
  </div>
  <div>
    <img :src="원룸[3].image" class="room-img">
    <h4>{{ 원룸[3].title }} 원룸</h4>
    <p>{{원룸[3].price}}원</p>
  </div>
  <div>
    <img :src="원룸[4].image" class="room-img">
    <h4>{{ 원룸[4].title }} 원룸</h4>
    <p>{{원룸[4].price}}원</p>
  </div>
  <div>
    <img :src="원룸[5].image" class="room-img">
    <h4>{{ 원룸[5].title }} 원룸</h4>
    <p>{{원룸[5].price}}원</p>
  </div>
</template>

<script>
import data from './assets/post.js';

export default {
  name: 'App',
  data(){
    return{
      원룸 : data,
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
  padding:20px;
}
.room-img {
  width: 70%;
  margin-top: 40px;
}
</style>
