<template>
  <div class="container py-5">
    <div class="row">
         <AlbumCard v-for="(cardInfo,index) in cardsInfo" 
        :key="index"
        :cardInfo="cardInfo"
        />
    </div>   
  </div>
</template>

<script>
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
    },
    methods:{
        getCardInfo() {
              axios.get('https://flynn.boolean.careers/exercises/api/array/music')
                .then( (result) => {   
                    this.cardsInfo = result.data.response;             
                    console.log(this.cardsInfo[5].author)
                    })
        },
    },
    created(){
        this.getCardInfo();
    }
}
</script>

<style lang="scss">

</style>