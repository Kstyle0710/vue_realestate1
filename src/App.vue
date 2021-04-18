<template>
  <div class="menu">
    <!-- 반복을 쌩으로 한다면 -->
    <!-- <a href="">Home</a>
    <a href="">Products</a>
    <a href="">About</a> -->

    <!-- 반복문 사용, key 값을 반드시 설정해줘야 한다.-->
    <a v-for="(menu, i) in menus" :key="i" href="">{{menu}} {{i}}</a>


  </div>


  <!-- <div>
    <h4 class='red' :style="style1">종로 원룸</h4>
    <p>{{price1}}</p>
    <p>{{products[1]}}</p>  
  </div>
  <div>
    <h4>강남 원룸</h4>
    <p>{{price2}}</p>
    <p>{{products[0]}}</p>  
  </div> -->

  <div v-for="(info, i) in products" :key="i">
    <h4>허위 매물 정보</h4>
    <p>{{products[i]}}</p>
    <p>{{price[i]}}</p>
  </div>


</template>

<script>


export default {
  name: 'App',
  data(){
    return {
      products : ['역삼동 원룸', '천호동 원룸', '군산 원룸'],
      price : [100, 70, 60],
      style1 : 'color : blue',
      
      menus : ['Home', 'Product', 'About'],

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
  color: #3a76b3;
  margin-top: 30px;
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
