<template>
  <div>
    <Header />
    <ListDiscs :list-discs = "listDiscs"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import ListDiscs from './components/Discs.vue'

import axios from 'axios';

export default {
  name: 'App',
  components: {
    Header,
    ListDiscs,
  },
  data()
  {
    return{
      uriCall:'https://flynn.boolean.careers/exercises/api/array/music',
      listDiscs:[],
    }
  },
  methods:
  {
      getMusicDiscs(uriCall)
      {
          axios.get(uriCall).then(res =>{

            this.listDiscs = res.data.response;
          });
      }
  },
  mounted()
  {
    this.getMusicDiscs(this.uriCall);
  }
}
</script>

<style lang="scss">
@import 'assets/scss/index.scss';

</style>
