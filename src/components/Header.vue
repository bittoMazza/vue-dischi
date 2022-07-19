<template>
  <header>
    <div class="header-container">
        <i class="bi bi-spotify spotify-icon"></i>
    </div>
  </header>
</template>

<script>
export default {

}
</script>

<style lang="scss">
@import "../styles/variables.scss";

.header-container{
    background-color: $secondaryColor;
    .spotify-icon{
        font-size:40px;
        margin-left: 30px;
        color: #1DB954;
    }
}
</style>