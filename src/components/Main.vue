<template>
  <main>
    <AlbumsContainer/>
  </main>
</template>

<script>
import AlbumsContainer from "./AlbumsContainer.vue" 
export default {
    components:{
        AlbumsContainer,
    }
}
</script>

<style lang="scss">
@import "../styles/variables.scss";
main{
    background-color: $mainColor;
}
</style>