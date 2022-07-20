<template>
  <div class="container py-5">
    <Loading v-if="IsLoadingScreen == true"/>
    <div v-eslse>
        <SelectedGenre
        :albums="cardsInfo" @selectGenre="SearchByGenre"/>
        <div class="row">
            <AlbumCard v-for="(cardInfo,index) in cardsInfo" 
            :key="index"
            :cardInfo="cardInfo"
            />
        </div> 
    </div>   
  </div>
</template>

<script>
import Loading from "./Loading.vue"
import AlbumCard from "./AlbumCard.vue"
import SelectedGenre from "./SelectedGenre.vue"
import axios from 'axios'
export default {
    data:function(){
        return{
            cardsInfo:[],
            IsLoadingScreen:true,
            filteredCards:[],
        }
    },
    components:{
        AlbumCard,
        Loading,
        SelectedGenre,
    },
    methods:{
        getCardInfo() {
              axios.get('https://flynn.boolean.careers/exercises/api/array/music')
                .then( (result) => {   
                    this.cardsInfo = result.data.response;    
                     this.IsLoadingScreen = false;        
                    })                   
                .catch((error) => {
                    console.warn(error)
                })
        },
        SearchByGenre(){
            this.filteredCards = [...this.cardsInfo];
            this.filteredCards.filter ( (album) => album)
        }
    },
    created(){
        setTimeout(this.getCardInfo,3000);
    }
}
</script>

<style lang="scss">

</style>