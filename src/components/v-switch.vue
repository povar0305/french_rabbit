<template>

      <input
        type="checkbox"
        name="toggle"
        class="switch__input"
        v-model="status"
        @change="changeCheckbox"
      />
    
</template>
<script>
export default {
  name: "v-switch",
  props: {
    switch_status:Boolean,
  },
  data() {
    return {
      status: Boolean,
    };
  },
  methods: {
    changeCheckbox() {
      this.$emit("changeCheckbox", {
        status: this.status,
      });
    },
  },
  mounted() {
    this.status = this.switch_status;
    console.log("this.switch_status",this.switch_status)
  },
};
</script>
<style lang="scss" scouped>

input{
      display: none;
    }
</style>