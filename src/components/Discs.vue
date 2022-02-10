<template>
    <main class="container d-flex justify-content-center align-items-center flex-wrap">
            <DiscCard 
                v-for="(listDisc,index) in listDiscs" 
                :key="index" 
                :author = "listDisc.author"
                :poster = "listDisc.poster"
                :title = "listDisc.title"
                :year = "listDisc.year"
                
            />
    </main>
</template>
<script>
import DiscCard from "./DiscCard.vue"

export default {
    name:'Discs',
    props:['listDiscs'],
    components: {
    DiscCard,
  },
}
</script>

<style lang="scss" scoped>

</style>