<template>
  <button
    class="button-foodies"
    :class="{
      '-primary': primary,
      '-outline': outline,
      '-flat': flat,
      '-translucent': translucent,
      '-large': large,
      '-small': small,
      '-block': block,
    }"
    @click="$emit('btnAct')"
  >
    <span class="textbutton content"> <slot /> </span>
    <span class="material-symbols-outlined textbutton"> east </span>
  </button>
</template>

<script>
export default {
  name: "ButtonFoodies",

  props: {
    primary: Boolean,
    outline: Boolean,
    flat: Boolean,
    translucent: Boolean,
    large: Boolean,
    small: Boolean,
    block: Boolean,
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/styles/variables.scss";

.button-foodies {
  display: flex;
  height: 68px;
  padding: 25px;
  align-items: center;
  justify-content: center;
  column-gap: 10px;

  font-family: "Inter";

  border: 0;
  cursor: pointer;
  transition: all 0.2s ease-in;

  background: map-get($colors, "primary");
  color: map-get($colorsText, "primary");

  &:active {
    filter: brightness(75%);
  }

  &.-primary {
    background: map-get($colors, "primary");
    color: map-get($colorsText, "primary");

    &:hover {
      background: map-get($activeColors, "primary");
    }
  }

  &.-outline.-primary {
    background: #fff;
    padding: calc(25px - 2px);
    color: map-get($colors, "primary");
    border: 2px solid map-get($colors, "primary");

    &:hover {
      background: map-get($colors, "primary");
      color: map-get($colorsText, "primary");
    }
  }

  &.-flat.-primary {
    background: none;
    // filter: brightness(50%);
    line-height: 17px;
    padding: calc(25px - 2px);
    color: map-get($colors, "primary");

    &:hover {
      .content {
        line-height: 22px;
        border-bottom: 1px solid;
      }
    }
  }

  &.-translucent.-primary {
    background: none;
    filter: brightness(75%);
    border: 0;
    color: map-get($colors, "primary");
  }

  &.-large {
    padding: 0.5rem 1rem;
    font-size: 1.25rem;
    line-height: 1.5;
    height: 100%;
  }

  &.-small {
    padding: 0.25rem 0.5rem;
    font-size: 15px;
    line-height: 18px;
    height: 42px;
  }

  &.-block {
    width: 100%;
    flex-basis: 100%;
    flex-grow: 1;
  }

  > .textbutton {
    font-size: 16px;
  }
}
</style>
