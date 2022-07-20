<template>
  <select name="selectType" id="">
    <option @change="$emit('selectGenre',card.genre)" or="(card,index) in albums" :key="index" value=""> {{ card.genre }}</option>
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