<template>
  <div class="container py-5">
    <Loading v-if="IsLoadingScreen == true"/>
    <div v-else>
        <div class="d-flex justify-content-around">
            <SelectedGenre
            :albums="albumsGenre" 
            @selectGenre="SearchByGenre"/>
            <SelectedArtist
            :albums="albumsArtist"
            @selectArtist="SearchByArtist"/>
        </div>
        <div class="row">
            <AlbumCard v-for="(cardInfo,index) in filteredCards" 
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
import SelectedArtist from "./SelectedArtist.vue"
import axios from 'axios'
export default {
    data:function(){
        return{
            cardsInfo:[],
            IsLoadingScreen:true,
            filteredCards:[],
            albumsGenre:[],
            albumsArtist:[],
        }
    },
    components:{
        AlbumCard,
        Loading,
        SelectedGenre,
        SelectedArtist,
    },
    methods:{
        getCardInfo() {
              axios.get('https://flynn.boolean.careers/exercises/api/array/music')
                .then( (result) => {   
                    this.cardsInfo = result.data.response;   
                    this.filteredCards = this.cardsInfo 
                    this.createGenreArray(this.filteredCards);
                    this.createArtistArray(this.filteredCards);
                     this.IsLoadingScreen = false;        
                    })                   
                .catch((error) => {
                    console.warn(error)
                })
        },
        SearchByGenre(genre){
            this.filteredCards = [...this.cardsInfo].filter( (album) => album.genre.includes(genre))
        },
        SearchByArtist(artist){
            this.filteredCards = [...this.cardsInfo].filter( (album) => album.author.includes(artist))
        },
        createGenreArray(albumArray){
            for(let i = 0; i < albumArray.length ; i++){
                if(!this.albumsGenre.includes(albumArray[i].genre)){
                    this.albumsGenre.push(albumArray[i].genre);
                }
            }
        },
         createArtistArray(albumArray){
            for(let i = 0; i < albumArray.length ; i++){
                if(!this.albumsArtist.includes(albumArray[i].author)){
                    this.albumsArtist.push(albumArray[i].author);
                }
            }
        },
        
    },
    created(){
        setTimeout(this.getCardInfo,3000);
    }
}
</script>

<style lang="scss">

</style>