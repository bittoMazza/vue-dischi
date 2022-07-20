<template>
  <select name="selectType" @change="$emit('selectGenre','rock')" id="">
    <option v-for="(card,index) in albums" :key="index" value='rock'> {{ card }}</option>
  </select>
</template>

<script>
export default {
    props:[
        'albums'
    ]
}
</script>

<style>

</style>