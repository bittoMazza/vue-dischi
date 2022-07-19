<template>
    <div class="card-album">
         <img class="w-100" :src="cardInfo.poster" alt="Card image cap">
         <h4 class="album-title" >{{ cardInfo.title }}</h4>
         <div class="text-muted">
            <span class="d-block fs-5">
                {{cardInfo.author}}
            </span>
            <span>{{cardInfo.year}}</span>
         </div>
    </div>
</template>

<script>
export default {
    props:['cardInfo'],
}
</script>

<style lang="scss" scoped>
@import "../styles/variables.scss";
    .card-album{
        text-align: center;
        padding: 20px;
        margin: 12px 20px;
        width: calc((100% / 5) - 40px);
        background-color: $secondaryColor;
        .album-title{
            color: white;
            padding: 20px 0;
            text-transform: uppercase;
        }
        

    }
</style>