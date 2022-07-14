<template>

  <div class="black_bg" v-if="모달창열렸니 == true">
    <div class="white_bg">
      <h4>상세페이지</h4>
      <p>내용내용내용</p>
      <button class="close" @click="모달창열렸니 = false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a href="" v-for="작명 in menu" :key="작명">{{ 작명 }}</a>
    <!-- <a href="">Home</a> -->
    <!-- <a href="">Shop</a> -->
    <!-- <a href="">About</a> -->
  </div>

  <!-- <button>
    <span>공지<br>사항</span>
  </button>
  <button>
    <span>공지<br>사항</span>
  </button> -->
  
  <div @click="모달창열렸니 = true">
    <img src="./assets/room0.jpg" alt="">
    <h4>{{ products[0] }}</h4>
    <p>{{ price1 }}만원</p>
    <button @click="신고수[0] += 1">허위매물신고</button> <span>신고수 : {{ 신고수[0] }}</span>
  </div>

  <div>
    <img src="./assets/room1.jpg" alt="">
    <h4>{{ products[1] }}</h4>
    <p>{{ price2 }}만원</p>
    <button @click="신고수[1] += 1">허위매물신고</button> <span>신고수 : {{ 신고수[1] }}</span>
  </div>
  
  <div>
    <img src="./assets/room2.jpg" alt="">
    <h4>{{ products[2] }}</h4>
    <p>{{ price3 }}만원</p>
    <button @click="신고수[2] += 1">허위매물신고</button> <span>신고수 : {{ 신고수[2] }}</span>
  </div>

  
  <!-- 반복문을 이용 -->
  <!-- <div v-for="(a, i) in products" :key="i">
    <h4  :style="스타일">{{ a }}</h4>
    <p>{{ price2 }}만원</p>
  </div> -->

</template>

<script>


export default {
  name: 'App',
  data(){
    return {
      //데이터 보관함
      
      price1 : 60,
      price2 : 70,
      price3 : 80,
      스타일 : 'color : blue', // 스타일 데이터로 저장
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      menu : ['Home', 'Shop', 'About'],
      신고수 : [0, 0, 0], //
      모달창열렸니 : false,
    }
  },
  // methods : {
  //   increase(){
  //     this.신고수 += 1 //this 꼭써야함 data를 뜻함
  //   }
  // },
  components: {
  }
}
</script>

<style>

body{margin: 0;}

div{box-sizing: border-box;}

.black_bg{position: fixed;width: 100%;height: 100%;padding: 20px;background: rgba(0, 0, 0, 0.5);}
.white_bg{width: 50%;padding: 20px;margin: 0 auto;background: #fff;border-radius: 10px;}


#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu{background: darkslateblue;padding: 15px;border-radius: 5px;}
.menu a{color: #fff;padding: 10px;text-decoration: none;}
/* button{position:relative;width: 50px;height: 50px;padding:1px;margin-right: 10px;background-color: #e1e1e1;border: none;border-radius: 15px;overflow: hidden;}
button:before{display: block;position:absolute;top: 0;left: 0;width:0;height: 0;background: #000;content: '';transition: all ease-in-out 0.5s;}
button:hover:before{width:100%;height: 100%;}
button span{position: absolute;top: 1px;left: 1px;width: calc(100% - 2px);height: calc(100% - 2px);background: #fff;border-radius: 13px;vertical-align: middle;} */

img{margin-top: 40px;}



</style>
