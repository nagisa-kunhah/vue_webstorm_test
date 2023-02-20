<template>
  <div id="wrap">
    <div id="space1">
      <div id="MySwiper">
        <swiper :modules="modules" :pagination="{ clickable: true }">
          <swiper-slide v-for="pic in pictures" >
            <div id="Swiper_Per">
              <img id="Swiper_Per_img" :src="pic" alt="ok">
            </div>
          </swiper-slide>
        </swiper>
      </div>
      <div id="recommend">
        <div id="recommend_per">
          <img :src="pictures[0]" id="recommend_per_img" alt="ok">
        </div>
        <div id="recommend_per"></div>
        <div id="recommend_per"></div>
        <div id="recommend_per"></div>
        <div id="recommend_per"></div>
        <div id="recommend_per"></div>
      </div>
    </div>
<!--    <button @click="changePic">按钮</button>-->
  </div>
<!--    <source srcset="./src/assets/pic.webp">-->
</template>

<script>
import SwiperClass, { Pagination } from 'swiper'
import { Swiper, SwiperSlide } from 'vue-awesome-swiper'
import 'swiper/css'
import 'swiper/css/pagination'
export default {
  name: "MainPage",
  data(){
    return{
      value:0.6,
      pictures:["./src/assets/pic.webp","pic2","pic3","pic4"],
    }
  },
  components: {
    Swiper,
    SwiperSlide
  },
  watch:{
    pictures:{
      handler(newValue,OldValue){
        console.log("ok")
      },
      deep:true
    }
  },
  methods:{
    changePic(){
      this.pictures[0]="aa"
    }
  },
  setup() {
    return {
      modules: [Pagination]
    }
  }
}
</script>

<style scoped>
#wrap{
  width: 1200px;
  background-color: red;
}
#space1{
  display: flex;
  height: 320px;
  background-color: blue;
  margin-top: 30px;
  padding: 10px;
}
#MySwiper{
  display: flex;
  justify-content: center;
  width: 533px;
  background-color: green;
}
#Swiper_Per{
  text-align: center;
}
#recommend{
  display: flex;
  background-color: orange;
  width: 100%;
  margin-left:10px;
  flex-wrap: wrap;
  justify-content: space-between;
  align-content: space-between;
}
#recommend_per{
  display: flex;
  background-color: white;
  width: 200px;
  height: 130px;
  object-fit: inherit;
}
#recommend_per_img{
  width: 100%;
  border-radius: 10px;
  /*height: auto;*/
  object-fit: inherit;
}
#Swiper_Per_img{
  object-fit: inherit;
  width: 100%;
  height: 100%;
}
</style>