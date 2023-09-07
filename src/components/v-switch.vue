<template>
      <input type="checkbox"  v-bind:value="value" 
      v-on:change="$emit('input', $event.target.value)" />
</template>
<script>
export default {
  name: "v-switch",
  props: {
    value:Boolean
  },
  data(){
    return{
     // status:this.value
    }
  },mounted() {
    console.log(this.value)
  },
  
};
</script>
<style scoped lang="scss">
input {
  display: none;
}
</style>