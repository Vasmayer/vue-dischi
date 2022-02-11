<template>
    <header class="d-flex justify-content-around align-items-center">
        <img src="../assets/img/logo.png" alt="Logo Spotify" class="img-fluid">
        <Select />
    </header>
</template>
<script>

import Select from './Select.vue'

export default {
    name: 'App',
  components: {
    Select,
  },
}
</script>

<style lang="scss" scoped>

@import '../assets/scss/_vars.scss';

header
{
    background-color: $header-background;

    img{
        height: 80px;
        width: auto;
        padding: 20px 10px;
    }
    select{
        width: 300px;
        height: 40px;
    }
}
</style>