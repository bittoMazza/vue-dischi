<template>
  <div class="container py-5">
    <Loading/>
    <div class="row">
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