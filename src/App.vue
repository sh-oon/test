<template>
  <div class="wrap clear">
    <nav class="gnb">
      <ul>
        <li class="mm" v-for="main in menu" :key="main"><a href="#">{{ main }}</a></li>
      </ul>
    </nav>
    <div class="content clear">
      <div class="name_price left clear" v-for="(product,t) in products" :key="t">
        <h3 :style="stl">{{ products[t] }} </h3>
        <p>{{ priceArr[t] }} won</p>
        <button @click="point[t]++">허위매물 신고</button>
        <span>신고수 : {{ point[t] }}</span>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return{
      priceArr: [60000,40000,30000],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      stl: "color : blue",
      point : [0,0,0],
      menu : ['Home', 'Product', 'About', 'Contact']
    }
  },
  methods : {

  },
  components: {
    
  }
}
</script>

<style>
* {padding: 0; margin: 0;}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.left {float: left;}
.clear::after {content: ''; display: block; clear: both;}
.wrap {width: 100vw; height: 100vh;}
.content {width: 100%; height: 100%;}
.name_price {width: 330px; height: 50%; margin: 0 auto;}
ul, li {list-style: none;}
.gnb {width: 100%; height: 50px; background: darkslateblue; color: #ccc;}
.gnb ul {width: 60%; height: 100%; margin: 0 auto;}
.mm {display: block; width: 25%; height: 100%;float: left;}
.mm a {color: #ccc; text-decoration: none; line-height: 50px; text-align: center;}


</style>
