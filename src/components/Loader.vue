
<template>
   <div id="loading">
   <div class="spinner-border text-danger" role="status">
     <span class="visually-hidden">Loading...</span>
   </div>
   </div>
</template>
<script>
export default {
    name:'Loader',
    props:['isLoading'],
  }

</script>

<style lang="scss" scoped>
#loading
{
  position: fixed;
  top:0;
  left:0;
  right: 0;
  bottom: 0;
  background-color: rgba(#000,0.5);
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>