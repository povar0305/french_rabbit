<template>
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
</template>
<script>
export default {
  name: "v-switch",
  components: {},
};
</script>
<style lang="scss">
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