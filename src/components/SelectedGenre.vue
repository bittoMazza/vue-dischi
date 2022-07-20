<template>
  <select v-model="selected" name="selectType" @change="$emit('selectGenre',selected)" id="">
    <option v-for="(card,index) in albums" :key="index" :value='card'> {{ card }}</option>
  </select>
</template>

<script>
export default {
    props:[
        'albums'
    ],
    data: function() {
        return{
            selected: '',
        }
    }
}
</script>

<style>

</style>