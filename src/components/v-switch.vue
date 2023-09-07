<template>
  <div>
     <input type="checkbox" :checked="status" v-model="status"  :change="$emit('change', status)"
      />
  </div>
 
</template>
<script>
export default {
  name: "v-switch",
  props:{
    value:Boolean
  },
  data(){
    return{
      status:this.value
    }
  }
  
};
</script>
<style scouped>
input {
  display: none;
}
</style>