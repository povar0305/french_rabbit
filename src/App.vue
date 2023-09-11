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
              <span>Кухня под ключ</span>
            </vSwitch>
          </div>
          
          <a href="#" class="kitchen__link">
            <!-- <input type="checkbox" v-model="switch_status" />    -->
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
            <p>Тип кухни</p>
            <VChip></VChip>
          </div>
          <div class="kitchen__inner--col-1">
            <p>Цвет отделки</p>
            <VChip></VChip>
          </div>
        </div>
      </div>
      <vLine></vLine>
    </div>
  </div>
</template>

<script>
import VSwitch from "./components/v-switch";
import VChip from "./components/v-chip";
import vLine from "./components/v-line.vue";
import vSwitch from "./components/v-switch.vue";
export default {
  name: "App",
  components: {
    VSwitch,
    VChip,
    vSwitch,
    vLine,
  },
  data: function () {
    return {
      switch_status: false,
    };
  },
  methods: {
    
  },
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
