<template >
  <div class="chips">
    <slot></slot>
    <div class="chip">
      <label
        v-for="element in data"
        :key="element.value"
        :class="[{ circle: 'color' in element }, '']"
        :style="'color' in element ? { background: element.color } : ''"
        ><input
          type="radio"
          :value="element.value"
          v-on:input="$emit('input', element.value)"
          v-model="value"
        />
        <span v-if="!('color' in element)">
          {{ element.text }}
        </span>
      </label>
    </div>
  </div>
</template>
<script>
export default {
  name: "v-chip",
  props: {
    value: String,
    data: {
      color: String,
      text: String,
      value: String,
    },
  },
  data() {
    return {};
  },
};
</script>
<style lang="scss" scoped>
.chips {
  display: flex;
  flex-direction: column;
  & .chip {
    display: flex;
    flex-direction: row;
    & input {
      opacity: 0;
      position: absolute;
      left: -9999px;
    }
    & label:has(input:checked) {
      border: 1px solid #e84e0e;
      background-color: white;
    }

    & label {
      width: auto;
      border-radius: 32px;
      padding: 8px 24px;
      margin-right: 8px;
      background-color: #f2f2f2;
      cursor: pointer;
      transition: 0.35s cubic-bezier(0.54, 1.6, 0.5, 1);
      border: 1px solid transparent;
      & span {
        text-transform: uppercase;
        font-size: 12px;
        letter-spacing: 1.2;
        text-wrap: nowrap;
      }
      &.circle {
        border: 1px solid white;
        width: 32px;
        height: 32px;
        display: flex;
        align-items: center;
        justify-content: center;
        border-radius: 50%;
        cursor: pointer;
        padding-right: 8px;
        padding: 0;
        margin: 0;
      }
    }
  }
}
</style>