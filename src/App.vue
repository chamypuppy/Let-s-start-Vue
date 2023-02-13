<template>
  <div class="menu">
    <!-- <a v-for="(a, i) in 메뉴들" :key="i">{{ i }}</a> -->
    <a v-for="작명 in 메뉴들" :key="작명">{{ 작명 }}</a>
  </div>

  <div v-for="(a, i) in 3" :key="i">
    <h4>{{ products[i] }}</h4>
    <p>{{ price[i] }}만원</p>
  </div>
  
    <!-- 혹은 -->
  <div v-for="(a, i) in products" :key="i">
    <h4>{{ a }}</h4>
    <p>{{ price[i] }}만원</p>
  </div>
  
</template>

<script>

export default {
  name: 'App',
  data() { /* 데이터 보관함 - vue의 특징1 (데이터는 오브젝트 형태로 저장)*/
    return {
      price : [60, 70, 80],
      메뉴들 : ["Home", "Shop", "About"],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
    }
  },
  components: {
  }
}
</script>

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
  color: #fff;
  padding: 10px;
}

</style>
