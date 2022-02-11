<template>
    <div class="disc-card">
        <div class="disc-image">
            <img :src="poster" :alt="title" class="img-fluid">
        </div>
        <div class="disc-title">
            {{title}}
        </div>
         <div class="disc-author">
            {{author}}
        </div>
        <div class="disc-year">
            {{year}}
        </div>
    </div>
</template>

<script>
export default {
    name:'DiscCard',
    props:['title','poster','author','year'],
}
</script>

<style lang="scss" scoped>

@import '../assets/scss/_vars.scss';

.disc-card
{
    background-color: $cards-background;
    width: calc( ( 100% / 5 ) - 60px );
    font-size: 1.3rem;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
    height: 350px;
    margin: 30px;
    .disc-title
    {
        color: white;
        text-transform: uppercase;
        font-size: 1.3rem;
        width: 150px;
        padding: 20px 0;
        text-align: center;
    }
    .disc-image
    {
        width: 150px;
        height: 150px;
        padding: 15px;
    }
   
}
</style>