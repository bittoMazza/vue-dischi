<template>
  <div class="loading-container text-white">
    <span class="loading-text">ATTENDERE IL CARICAMENTO </span> 
    <div class="spinner-border" role="status">
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss">
    .loading-container{
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%,-50%);
        .loading-text{
            font-size: 40px;
        }
    }
</style>