<template>
<!-- 모달창 + 조건식 + 콜론 안붙임 -->
  <div class="black-bg" v-if="모달창상태==true">
    <div class="white-bg">
      <h4>상세 페이지</h4>
      <p>상세 페이지 내용임</p>
      <button @click="모달창상태 = false">닫기</button>
    </div>
  </div>


  <div class="menu">
    <a v-for="(menu, i) in menus" :key="i" href="">{{menu}} {{i}}</a>
  </div>


  <div v-for="(info, i) in products" :key="i">
    <h4>원룸 정보{{i+1}}</h4>
    <img src="https://picsum.photos/400/300?random=:i">
    <p @click="모달창상태=true">{{products[i]}}</p>
    <p>{{price[i]}}</p>

    <button @click="신고수[i]++">허위매물신고</button> <span>신고수 : {{신고수[i]}}</span>
    <button @click="increase(i)">추천</button> <span>추천수 : {{추천수[i]}}</span>

  </div>


</template>

<script>


export default {
  name: 'App',
  data(){
    return {
      모달창상태 : false,
      신고수 : [0, 0, 0],
      추천수 : [0, 0, 0],
      products : ['역삼동 원룸', '천호동 원룸', '군산 원룸'],
      price : [100, 70, 60],
      style1 : 'color : blue',      
      menus : ['Home', 'Product', 'About'],
    }
  },
  // 함수 만드는 공간
  methods : {
    increase(i){
      this.추천수[i] += 1;
    }
  },
  components: {   
  }
}
</script>

<style>
/* 모달창 스타일 */
body {
  margin : 0
}
div {
  box-sizing: border-box;
}
.black-bg {
  width:100%; height:100%;
  background: rgba(0,0,0,0.5);
  position:fixed; padding: 20px;
}
.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}

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
