<template>
  <div>
    <Loader :is-loading="isLoading" v-if="isLoading"/>
    <Header />
    <ListDiscs :list-discs = "listDiscs"/>
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
      isLoading:false
    }
  },
  methods:
  {
      getMusicDiscs(uriCall)
      {
          axios.get(uriCall).then(res =>{

            this.listDiscs = res.data.response;
            this.isLoading = false;
          });
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
