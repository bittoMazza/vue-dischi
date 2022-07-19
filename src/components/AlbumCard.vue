<template>
    <div class="card-album">
         <img class="card-img-top" :src="cardInfo.poster" alt="Card image cap">
         <h4 class="" >{{ cardInfo.title }}</h4>
         <div>
            <span class="d-block">
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
        margin: 10px 25px 0 25px;
        width: calc((100% / 5) - 50px);
        background-color: $secondaryColor;
    }
</style>