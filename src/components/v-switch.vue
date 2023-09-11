<template>
  <input type="checkbox" :checked="value"  v-on:change="this.updateValue" />
</template>
<script>
export default {
  name: "v-switch",
  props: {
    value: Boolean,
  },
  data() {
    return {
      // status:this.value
    };
  },
  mounted() {
    console.log(this.value);
  },
  methods: {
    updateValue(event) {
      this.$emit("change", event.target.checked);
    },
  },
};
</script>
<style scoped lang="scss">
input {
  display: none;
}
</style>