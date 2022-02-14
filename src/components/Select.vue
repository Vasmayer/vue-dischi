<template>
    <div>
        <select class="form-select" v-model="selected" @change="$emit('on-selected',selected)">
            <option value="" selected>Seleziona il Genere</option>
            <option :value="genre.toLowerCase()" v-for="(genre,index) in genres" :key="index" >{{genre}}</option>
            
        </select>
    </div>
</template>
<script>

export default {
    name:'Select',
    data()
    {
        return{
            selected:'',
        }
    },
    props:['genres'],
    methods:
    {
        
    }
}
</script>

<style lang="scss" scoped>

</style>