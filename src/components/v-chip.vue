<template >
  <div class="chips" :class="data.type">
    <slot></slot>
    <div class="chip">
      <label v-for="element in data.data" :key="element"
        ><input
          type="radio"
          :name="data.name_group"
          :value="element"
          v-on:change="$emit('change', $event.target.value)"
        />
        <span v-if="data.type == 'texts'" class="text">{{ element }}</span>
        <span
          v-if="data.type == 'colors'"
          class="circle"
          :style="{ background: element }"
        ></span>
      </label>
    </div>
  </div>
</template>
<script>
export default {
  name: "v-line",
  props: {
    data: {
      type: String, //Тип выбор цвета colors или текст texts
      name_group: String, // Название группы радио кнопок
      data: Array, //данные для вывода радио кнопок
    },
  },
};
</script>
<style lang="scss" scoped>
.chips {
  display: flex;
  flex-direction: column;
  & input {
    opacity: 0;
    position: absolute;
    left: -9999px;
  }
  & label:has(input:checked) {
    border: 1px solid #e84e0e;
    background-color: transparent;
  }

  & label {
    border: 1px solid transparent;
  }

  & .chip {
    display: flex;
    flex-direction: row;
  }
  &.texts label {
    width: auto;
    border-radius: 32px;
    padding: 8px 24px;
    margin-right: 8px;
    background-color: #f2f2f2;
    cursor: pointer;
    transition: 0.35s cubic-bezier(0.54, 1.6, 0.5, 1);
    border: 1px solid transparent;
    & span.text {
      text-transform: uppercase;
      font-size: 12px;
      letter-spacing: 1.2;
    }
  }

  &.colors label {
    position: relative;
    width: 32px;
    height: 32px;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 50%;
    cursor: pointer;
    & span.circle {
      position: absolute;
      width: 24px;
      height: 24px;
      border-radius: 50%;
    }
  }
}
</style>