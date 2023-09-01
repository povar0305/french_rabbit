<template>
  <div id="app">
    <div class="kitchen">
      <vLine></vLine>
      <div class="kitchen__inner">
        <div class="kitchen__inner--row">
          <vSwitch></vSwitch>
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
            <p>Тип кухни</p>
            <div class="kitchen__inner--chips types">
              <div class="kitchen__inner--chip">
                <label
                  ><input
                    type="radio"
                    value="standart"
                    checked
                    name="selectedTypeKitchen"
                  />
                  Cтандарт
                  </label
                >
              </div>
              <div class="kitchen__inner--chip">
                <label>
                  <input type="radio" value="plus" name="selectedTypeKitchen" />
                  Плюс
                  </label
                >
              </div>
            </div>
          </div>
          <div class="kitchen__inner--col-1">
            <p>Тип кухни</p>
            <div class="kitchen__inner--chips colors">
              <div class="kitchen__inner--chip">
                <input
                  type="radio"
                  value="#D3C285"
                  checked
                  id="#D3C285"
                  name="selectedColorKitchen"
                />
                <label for="#D3C285">&nbsp </label>
              </div>
              <div class="kitchen__inner--chip">
                <input
                  type="radio"
                  value="#CBB697"
                  checked
                  id="#CBB697"
                  name="selectedColorKitchen"
                />
                <label for="#CBB697">&nbsp </label>
              </div>
            </div>
          </div>
        </div>
      </div>
      <vLine></vLine>
    </div>
  </div>
</template>

<script>
import vLine from "./components/v-line.vue";
import vSwitch from "./components/v-switch.vue";
export default {
  name: "App",
  components: { vSwitch, vLine },
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
    &--chips {
      display: flex;
      & input {
        opacity: 0;
        position: absolute;
        left: -9999px;
        &:checked + label {
          border: 1px solid #e84e0e;
          background-color: transparent;
        }
      }
      &.types label {
        width: auto;
        border-radius: 32px;
        padding: 8px 24px;
        margin-right: 8px;
        background-color: #f2f2f2;
        text-transform: uppercase;
        font-size: 12px;
        cursor: pointer;
        transition: 0.35s cubic-bezier(0.54, 1.6, 0.5, 1);
        border: 1px solid transparent;
        letter-spacing: 1.2;
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
        &::after {
          position: absolute;
          width: 24px;
          height: 24px;
          border-radius: 50%;
          content: "";
          background-color: #d3c285 !important;
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
