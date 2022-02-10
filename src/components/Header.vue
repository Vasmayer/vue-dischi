<template>
    <header>
        <img src="../assets/img/logo.png" alt="Logo Spotify" class="img-fluid">
    </header>
</template>
<script>

export default {
    name:'Header'
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
}
</style>