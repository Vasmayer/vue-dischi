<template>
    <div>
        <select class="form-select" @change="getSelected($event)" >
            <option value="" selected>Seleziona il Genere</option>
            <option value="rock">Rock</option>
            <option value="pop">Pop</option>
            <option value="jazz">Jazz</option>
            <option value="metal">Metal</option>
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
    methods:
    {
        getSelected(e) 
        {
            const value = e.target.value
            if(value)
            {
              this.selected = value;
              console.log(e.target.value);
            }
           
        },
    }
}
</script>

<style lang="scss" scoped>

</style>