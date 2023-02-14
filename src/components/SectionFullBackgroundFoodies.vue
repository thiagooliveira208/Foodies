<template>
  <div class="section-full-background-foodies">
    <div class="textcontent">
      <div class="description">
        {{ description }}
      </div>

      <button-foodies v-if="actionButton" class="action-button-block" primary>
        {{ actionButtonText }}
      </button-foodies>
    </div>

    <button-foodies v-if="actionButton" class="action-button" primary>
      {{ actionButtonText }}
    </button-foodies>
  </div>
</template>

<script>
import ButtonFoodies from "@/components/ButtonFoodies.vue";

export default {
  name: "SectionFullBackgroundFoodies",

  components: {
    ButtonFoodies,
  },

  props: {
    description: {
      type: String,
      default: "",
    },
    actionButton: {
      type: Boolean,
      default: false,
    },
    actionButtonText: {
      type: String,
      default: "",
    },
  },
};
</script>

<style lang="scss" scoped>
.section-full-background-foodies {
  display: flex;
  position: relative;
  flex-direction: row;
  align-items: center;

  margin-top: 50px;
  right: 30px;

  height: 459px;
  width: 100vw;

  font-family: "Inter";

  background: linear-gradient(0deg, rgba(2, 2, 2, 0.59), rgba(2, 2, 2, 0.59)),
    url("@/assets/images/food/vegetais_footer.png");
  background-position: center;
  background-repeat: no-repeat;

  > .textcontent {
    order: 10;

    padding: 10%;
    text-align: center;

    > .description {
      margin: 18px 0;
      font-size: 35px;
      font-weight: 500;
      line-height: 42px;
      color: #ffffff;
    }

    > .action-button-block {
      width: 100%;
      margin-top: 50px;
      order: 20;
    }
  }

  > .action-button {
    display: none;
    order: 20;
  }
}

@media (min-width: 769px) {
  .section-full-background-foodies {
    flex-direction: column;
    justify-content: center;
    background-size: cover;
    max-width: 100%;
    max-height: 459px;
    height: auto;
    right: 0;
    margin: 0;

    > .textcontent {
      order: 10;

      // padding: 10%;
      // text-align: center;

      > .description {
        margin: 18px 0;
        font-size: 60px;
        font-weight: 600;
        line-height: 73px;
        color: #ffffff;
      }

      > .action-button-block {
        display: none;
      }
    }

    > .action-button {
      display: flex;
      width: 210px;
      margin-bottom: 87px;
    }
  }
}
</style>
