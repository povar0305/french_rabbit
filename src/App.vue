<template>
  <div id="app">
    <div class="kitchen">
      <vLine></vLine>
      <div class="kitchen__inner">
        <div class="kitchen__inner--row">
          <div class="kitchen__inner--switch">
            <label>
              <vSwitch v-model="checked"></vSwitch>
              <span>Кухня под ключ {{ checked }} </span>
            </label>
          </div>
          <a href="#" class="kitchen__link">
      <!-- <input type="checkbox" v-model="checked" />    -->
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
      checked:true
    };
  },
  methods: {
    input(data){
      console.log(data)
    }
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
      & label {
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
