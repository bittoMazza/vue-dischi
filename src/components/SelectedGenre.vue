<template>
<div class="my-4">
    <select class="W-100 rounded" v-model="selected" name="selectType" @change="$emit('selectGenre',selected)" id="">
        <option value="" disabled selected>SELEZIONA CHE GENERE VUOI ASCOLTARE !!</option>
        <option value="" class="text-danger">RESET RICERCA PER GENERE</option>
        <option v-for="(card,index) in albums" :key="index" :value='card'> {{ card }}</option>
    </select>
</div>
 
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

<style lang="scss">
 select{
    margin: 30px 0;
    padding: 10px;
    text-align: center;
    
 }
</style>