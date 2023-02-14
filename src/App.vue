<template>

<div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>상세페이지 내용</p>
      <button @click="모달창열렸니 = false">닫기</button>
    </div>
  </div>





  <div class="menu">
    <!-- <a v-for="(a, i) in 메뉴들" :key="i">{{ i }}</a> -->
    <a v-for="작명 in 메뉴들" :key="작명">{{ 작명 }}</a>
  </div>



  <div>
    <img src="./assets/room0.jpg" class="room-img"/>
    <h4  @click="모달창열렸니 = true">{{products[0]}}</h4>
    <p>{{ price1 }} 만원</p>
    <button @click="신고수[0]++">허위매물신고</button>
    <span>신고 수 : {{신고수[0]}}</span>
  </div>



  <div>
    <img src="./assets/room1.jpg" class="room-img"/>
    <h4>{{products[1]}}</h4>
    <p>{{ price2 }} 만원</p>
    <button @click="신고수[1]++">허위매물신고</button>
    <span>신고 수 : {{신고수[1]}}</span>
  </div>

  <div>
    <img src="./assets/room2.jpg" class="room-img"/>
    <h4>{{products[2]}}</h4>
    <p>{{ price2 }} 만원</p>
    <button @click="신고수[2]++">허위매물신고</button>
    <span>신고 수 : {{신고수[2]}}</span>
  </div>

</template>

<script>
// import 

export default {
  
  name: 'App',
  data() { /* 데이터 보관함 - vue의 특징1 (데이터는 오브젝트 형태로 저장)*/
    return {
      모달창열렸니 : false, /* 리액트에서는 이러한 데이터 보관함을 state라고 한다. true(혹은 0)가 열린상태, false(혹은 1)가 닫힌 상태.  */
      신고수 : [0, 0, 0],
      price1 : 60,
      price2 : 70,
      메뉴들 : ["Home", "Shop", "About"],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
    }
  },
  methods : {
    increase(){
      this.신고수 += 1;
    }
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
.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed;
  padding: 20px;
}
.white-bg {
  width: 100%;
  background: #fff;
  border-radius: 8px;
  padding: 20px;
}




.room-img {
  width: 100%;
  margin-top: 40px;
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

</style>
