<template >
  <div class="chips">
    <slot></slot>
    <div class="chip">
      <label
        v-for="element in data.datas"
        :key="element.text"
        :class="[{ circle: element.hasOwnProperty('color')  }, text]"
        :style="element.hasOwnProperty('color')? { background: element.color } : ''"
        ><input
          type="radio"
          :name="data.name_group"
          :value="element.value"
          v-on:change="$emit('change', element.value)"
        />
        <span v-if="!element.hasOwnProperty('color') ">
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
    data: {
      type_group: String, //Тип выбор цвета colors или текст texts
      name_group: String, // Название группы радио кнопок
      datas: Array, //данные для вывода радио кнопок
    },
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