<template>
<div class="my-4">
    <select class="W-100 rounded" v-model="selected" name="selectType" @change="$emit('selectArtist',selected)" id="">
        <option value="" disabled selected>SELEZIONA L'ARTISTA CHE VUOI ASCOLTARE !!</option>
        <option value="" class="text-danger">RESET RICERCA PER ARTISTA</option>
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
    font-weight: bold;
    margin: 30px 0;
    padding: 10px;
    text-align: center;
    option{
        font-weight: bold;
    }
    
 }
</style>