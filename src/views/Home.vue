<template>
  <div class="home">
    <section_imgTxt :data="secData[0]" :order="'img-text'"> </section_imgTxt>
    <section_imgTxt :data="secData[1]" :order="'text-img'"> </section_imgTxt>
    <section_imgTxt :data="secData[2]" :order="'img-text'"> </section_imgTxt>
    <section_imgTxt :data="secData[3]" :order="'text-img'"> </section_imgTxt>
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
                title : "Rab",
                text : "Ke ke"
                
               },{   //definise da li ide slika levo ili desno u odnosu na tekst
                  imgLink : "https://i.pinimg.com/originals/b8/cf/63/b8cf6382e547e7376d4f914dd587cc73.jpg",
                  title : "Rab",
                  text : "Knjo knjo"
               },{
                 imgLink : 'https://i.pinimg.com/originals/83/be/c5/83bec55d24577a250cf51f9fa2ee7d3d.jpg',
                 title : "Rab",
                 text : "hnjo hnjo"
               },{
                 imgLink : 'https://i.pinimg.com/originals/35/b8/28/35b8286988cc55c4a6272c925cc33b5a.jpg',
                 title : "Rab",
                 text : "Kjni knji"
               }
               
               ]
    }
  }
}
</script>

<style scoped>
  .home{
    padding-top: 200px;
    background-color: black;
  }
</style>
