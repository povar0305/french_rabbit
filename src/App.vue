<template>
  <div id="app">
    <div class="kitchen">
      <div class="line"></div>
      <div class="kitchen__inner">
        <div class="kitchen__inner--row">
          <div class="switch">
            <input
              type="checkbox"
              name="toggle"
              class="switch__input"
              id="toggle-1"
            />
            <label for="toggle-1">
              <span>Кухня под ключ</span>
            </label>
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
              /></svg
          ></a>
        </div>
      </div>
      <div class="line"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
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
    padding-bottom: 24px;
    &--row {
      display: flex;
      flex-direction: row;
      justify-content: space-between;
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
.line {
  width: 100%;
  height: 1px;
  background-color: #e7e7e7;
}
.switch {
  display: flex;
  align-items: center;
  & input {
    &.switch__input {
      opacity: 0;
      position: absolute;
      left: -9999px;
      & + label {
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
      }
      &:checked {
        & + label:before {
          background: white;
        }
        & + label:after {
          left: 20px;
        }
      }
    }
  }
}
</style>
