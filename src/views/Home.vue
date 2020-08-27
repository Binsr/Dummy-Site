<template>
  <div class="home">
    <section_imgTxt id="sec1" :data="secData[0]" :order="'img-text'"> </section_imgTxt>
    <section_imgTxt :data="secData[1]" :order="'text-img'"> </section_imgTxt>
  </div>
</template>

<script>
// @ is an alias to /src
import section_imgTxt from '@/components/basic_components/sections/s_imgTx_01.vue'

export default {
  name: 'Home',
  components: {
    section_imgTxt
  },
  data(){
    return{
      secData: [{
                imgLink : 'https://i.pinimg.com/originals/32/17/38/3217387eb857e948175f4e7108411ab8.jpg',
                title : "order: img-text",
                text : "component name: s_imgTx_01"
                
               },{   //definise da li ide slika levo ili desno u odnosu na tekst
                  imgLink : "https://i.pinimg.com/originals/b8/cf/63/b8cf6382e547e7376d4f914dd587cc73.jpg",
                  title : "order: text-img",
                  text : "component name: s_imgTx_01"
               }]
    }
  }
}
</script>

<style scoped>
  .home{
    padding-top: 200px;
  }
</style>
