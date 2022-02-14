<template>
  <div>
    <Loader :is-loading="isLoading" v-if="isLoading"/>
    <Header @value-select = "getSelected" :genres="genres" />
    <ListDiscs :list-discs = "listDiscsFiltered"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import ListDiscs from './components/Discs.vue'
import Loader from './components/Loader.vue'

import axios from 'axios';

export default {
  name: 'App',
  components: {
    Header,
    ListDiscs,
    Loader,
  },
  data()
  {
    return{
      uriCall:'https://flynn.boolean.careers/exercises/api/array/music',
      listDiscs:[],
      listDiscsFiltered:[],
      isLoading:false,
      selected:'',
      genres:[]
    }
  },
  methods:
  {
      getMusicDiscs(uriCall)
      {
          axios.get(uriCall).then(res =>{

            this.listDiscs = res.data.response;
            this.listDiscsFiltered = res.data.response;
            this.isLoading = false;

            this.listDiscs.forEach(disc =>{

            if(!this.genres.includes(disc.genre)) this.genres.push(disc.genre)

            })

            
          });
      },
      getSelected(value)
      {
        this.selected = value;

        if(value)
        this.listDiscsFiltered = this.listDiscs.filter(disc => disc.genre.toLowerCase() === value)
       
      }
  },
  mounted()
  {
    this.isLoading = true;
    this.getMusicDiscs(this.uriCall);
  }
}
</script>

<style lang="scss">
@import 'assets/scss/index.scss';

</style>
