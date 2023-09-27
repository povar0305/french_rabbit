<template>
  <label>
    <input
      type="checkbox"
      :checked="modelValue"
      @change="$emit('update:modelValue', $event.target.checked)"
    />
  </label>
  <slot></slot>
</template>
  <script>
export default {
  name: "v-switch",
  props: { modelValue: Boolean }
};
</script>

  <style scoped lang="scss">
input {
  display: none;
}
label {
  user-select: none;
  height: 24px;
  width: 40px;
  position: relative;
  border-radius: 32px;
  cursor: pointer;
  border: 1px solid #e84e0e;
  background: #fff;
  margin-right: 16px;
  &:before {
    content: "";
    position: absolute;
    display: block;
    height: 24px;
    width: 24px;
    top: 0;
    left: 0;
    border-radius: 50%;
    transition: 0.2s;
  }
  &:after {
    content: "";
    position: absolute;
    display: block;
    height: 16px;
    width: 16px;
    top: calc((100% - 16px) / 2);
    left: 3px;
    border-radius: 32px;
    background: #e84e0e;
    transition: 0.35s cubic-bezier(0.54, 1.6, 0.5, 1);
  }

  span {
    white-space: nowrap;
    height: 24px;
    line-height: 24px;
    margin-left: 40px;
    padding-left: 16px;
  }
  &:has(input:checked) {
    &:before {
      background: white;
    }
    &:after {
      left: 20px;
    }
  }
}
</style>