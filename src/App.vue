<template>
  <div id="app">
    <div class="kitchen">
      <vLine></vLine>
      <div class="kitchen__inner">
        <div class="kitchen__inner--row">
          <div class="kitchen__inner--switch">
            <vSwitch
              v-bind:value="switch_status"
              @change="switch_status = $event"
            >
              <span>Кухня под ключ </span>
            </vSwitch>
          </div>
          <a href="#" class="kitchen__link">
            Подробнее
            <svg
              width="6"
              height="10"
              viewBox="0 0 6 10"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                fill-rule="evenodd"
                clip-rule="evenodd"
                d="M1.04482 0L0 1.05426L3.91037 5L0 8.94573L1.04482 10L6 5L1.04482 0Z"
                fill="#E84E0E"
              />
            </svg>
          </a>
        </div>
        <div class="kitchen__inner--row">
          <div class="kitchen__inner--col-1">
            <vChip :data="chip_kitchen" v-model="result_kitchen">
              <p>Тип кухни</p>
            </vChip>
          </div>
          <div class="kitchen__inner--col-1">
            <vChip :data="chip_color" v-model="result_colors">
              <p>Цвет отделки</p>
            </vChip>
          </div>
        </div>
      </div>
      <vLine></vLine>
    </div>
  </div>
</template>

<script>
import vSwitch from "./components/v-switch.vue";
import vChip from "./components/v-chip.vue";
import vLine from "./components/v-line.vue";
export default {
  name: "App",
  components: {
    vChip,
    vSwitch,
    vLine,
  },
  data: function () {
    return {
      switch_status: false,
      chip_kitchen: [
        { text: "Стандарт", value: "standart" },
        { text: "Плюс", value: "plus" },
      ],

      chip_color: [
        { text: "#D3C285", value: "D3C285", color: "#D3C285" },
        { text: "#CBB697", value: "CBB697", color: "#CBB697" },
        { text: "#DEE2E2", value: "DEE2E2", color: "#DEE2E2" },
        { text: "#DEDEDE", value: "DEDEDE", color: "#DEDEDE" },
        { text: "Без цвета", value: "Без цвета" },
      ],
      result_kitchen: "",
      result_colors: "CBB697",
    };
  },
  methods: {},
};
</script>

<style lang="scss">
@font-face {
  font-family: "Futura Futuris Light";
  src: url("./assets/FuturaFuturisC.ttf") format("truetype");
  font-weight: normal;
  font-style: normal;
}
#app {
  height: 100%;
  width: 100%;
}
.kitchen {
  max-width: 498px;
  font-family: "Futura Futuris Light";

  &__inner {
    padding-top: 24px;
    &--row {
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      padding-bottom: 24px;
    }
    &--col-1 {
      width: 50%;
      display: flex;
      flex-direction: column;
      & p {
        color: #959596;
        font-size: 16px;
        line-height: 20px;
        padding-bottom: 8px;
        margin: 0;
      }
    }
    &--switch {
      display: flex;
      align-items: center;
    }
  }
  &__link {
    font-size: 12px;
    letter-spacing: 1.2;
    color: #e84e0e;
    text-transform: uppercase;
    text-decoration: none;
    align-self: center;
    & svg {
      margin-left: 8px;
    }
  }
}
</style>
