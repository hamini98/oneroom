<template>

  <div class ="black-bg" v-if="modalStatus == true">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>내용</p>
      <button @click="modalStatus = false">닫기</button>
    </div>
  </div>
  
  <div class="menu">
    <a v-for="menus in menuarr" :key="menus">{{ menus }}</a>
  </div>
  <div >
    <img src="../assets/room0.jpg" class="room-img">
    <h4 class="red" :style="style2" @click="modalStatus = true">{{products[0]}}</h4>
    <p>{{price[0]}}</p>
    <button @click="increase">허위매물신고</button> <span>신고수 : {{ reportCount1 }}</span>
  </div>
  <div>
    <img src="../assets/room1.jpg" class="room-img">
    <h4>{{ products[1] }}</h4>
    <p>{{price[1]}}</p>
    <button @click="reportCount2++">허위매물신고</button> <span>신고수 : {{ reportCount2 }}</span>
  </div>
  <div>
    <img src="../assets/room2.jpg" class="room-img">
    <h4>{{ products[2] }}</h4>
    <p>{{ price[2]}}</p>
    <button @click="reportCount3++">허위매물신고</button> <span>신고수 : {{ reportCount3 }}</span>
  </div>
  
</template>

<script>


export default {
  name: 'HomeView',
  data(){ // data 보관
    return { // data는 object로 저장 : {자료이름:자료내용}
      modalStatus : false,
      menuarr : ['Home', 'Shop', 'About'],
      price : ['50만원', '60만원', '가격은 아무거나'],
      style2 : 'color:blue',
      products : ['역삼동 원룸', '천호동 원룸', '마포구 원룸'],
      reportCount1 : 0, reportCount2 : 0, reportCount3 : 0,
    }
  },
  methods: {
    increase(){
      this.reportCount1 += 1;
    }
  },
  components: {

  }
}
</script>

<style>

body {
  margin : 0
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


.menu {
  background : darkslateblue;
  padding : 15px;
  border-radius: 5px;
}
.menu a {
  color : white;
  padding : 10px;
}

.room-img {
  width: 100%;
  margin-top : 40px;
}
</style>
