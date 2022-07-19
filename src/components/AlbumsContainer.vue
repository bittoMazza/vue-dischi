<template>
  <div class="container py-5">
    <Loading v-if="loadingScreen == true"/>
    <div class="row" v-eslse>
         <AlbumCard v-for="(cardInfo,index) in cardsInfo" 
        :key="index"
        :cardInfo="cardInfo"
        />
    </div>   
  </div>
</template>

<script>
import Loading from "./Loading.vue"
import AlbumCard from "./AlbumCard.vue"
import axios from 'axios'
export default {
    data:function(){
        return{
            cardsInfo:[],
            loadingScreen:true,
        }
    },
    components:{
        AlbumCard,
        Loading
    },
    methods:{
        getCardInfo() {
              axios.get('https://flynn.boolean.careers/exercises/api/array/music')
                .then( (result) => {   
                    this.cardsInfo = result.data.response;    
                     this.loadingScreen = false;        
                    })                   
                .catch((error) => {
                    console.warn(error)
                })
        },
    },
    created(){
        setTimeout(this.getCardInfo,3000);
    }
}
</script>

<style lang="scss">

</style>