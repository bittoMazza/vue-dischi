<template>
  <div class="container">
    <AlbumCard v-for="(singleCard,index) in cardsInfo" :key="index"/>
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
                    console.log(this.cardsInfo)
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