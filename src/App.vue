<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div>
        <!-- html 속성 바인딩 구간 : 앞쪽에 콜론을 사용 -->
    <h4 class='red' :style="style1">종로 원룸</h4>
       <!-- 내용 데이터 바인딩 구간 : 쌍중괄호 -->
    <p>{{price1}}</p>
    <p>{{products[1]}}</p>  
  </div>
    <div>
    <h4>강남 원룸</h4>
    <p>{{price2}}</p>
    <p>{{products[0]}}</p>  
  </div>

</template>

<script>


export default {
  name: 'App',
  // 데이터 보관함 만들기 (return 중괄호 안에 데이터를 담는다)
  data(){
    return {
      price1 : 100,
      price2 : 70,
      style1 : 'color : blue',
      products : ['역삼동 원룸', '천호동 원룸', '군산 원룸'],

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
  margin-top: 60px;
}
</style>
