<template >
    <div class="chips types">
              <div class="chip">
                <label
                  ><input
                    type="radio"
                    value="standart"
                    checked
                    name="selectedTypeKitchen"
                  />
                  Cтандарт
                </label>
              </div>
              <div class="chip">
                <label>
                  <input type="radio" value="plus" name="selectedTypeKitchen" />
                  Плюс
                </label>
              </div>
            </div>
</template>
<script>
export default {
  name: "v-line",
};</script>
<style lang="scss" scoped>
.chips {
      display: flex;
      & input {
        opacity: 0;
        position: absolute;
        left: -9999px;
      }
      & label:has(input:checked) {
        border: 1px solid #e84e0e;
        background-color: transparent;
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
</style>