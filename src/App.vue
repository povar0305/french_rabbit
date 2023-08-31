<template>
  <div id="app">
    <div class="kitchen">
      <div class="line"></div>
      <div class="kitchen__inner">
        <div class="kitchen__inner--row">
          <div class="switch">
            <input type="checkbox" name="toggle" class="sw" id="toggle-1" />
            <label for="toggle-1"></label>
            <p>Кухня под ключ</p>
          </div>
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
    &.sw {
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
  & p {
    line-height: 20.8px;
    margin-bottom: 0;
    margin-top: 0;
  }
}
</style>
