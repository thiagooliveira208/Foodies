<template>
  <div class="content-variety">
    <img class="imagefood" :src="srcImgMain" />

    <div class="textcontent">
      <div v-if="title" class="title">
        {{ title }}
      </div>
      <div v-if="description" class="description">
        {{ description }}
      </div>
      <button-foodies v-if="actionButton" primary flat small>
        {{ actionButtonText }}
      </button-foodies>
    </div>
  </div>
</template>

<script>
import ButtonFoodies from "@/components/ButtonFoodies.vue";

export default {
  name: "ContentVarietyFoodies",

  components: {
    ButtonFoodies,
  },

  props: {
    title: {
      type: String,
      default: "",
    },
    description: {
      type: String,
      default: "",
    },
    srcImg: {
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

  data() {
    return {
      srcImgMain: require(`@/assets/images/${this.srcImg}`),
    };
  },
};
</script>

<style lang="scss" scoped>
.content-variety {
  display: flex;
  flex-direction: column;
  // width: 310px;
  font-family: "Inter";

  > .imagefood {
    // width: 100%;
    width: 310px;
    max-height: 100%;
  }

  > .textcontent {
    padding: 13%;
    // width: 310px;
    background: #f0f1ec;

    border: 1.5px solid #06c167;

    > .title {
      font-size: 32px;
      font-weight: 500;
      line-height: 39px;
      color: #1d1d1f;
    }

    > .description {
      margin: 25px 0;
      font-size: 16px;
      font-weight: 400;
      line-height: 19px;
      color: #1d1d1f;
    }
  }
}

@media screen and (min-width: 768px) {
  .content-variety {
    flex-direction: row;

    > .imagefood {
      width: 290px;
      // height: 290px;
    }

    > .textcontent {
      padding: 0;
      width: 290px;
      height: 290px;

      > .title {
        padding-top: 37px;
        padding-left: 37px;
      }

      > .description {
        padding-left: 37px;
      }
    }
  }
}
</style>
