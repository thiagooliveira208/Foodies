<template>
  <div class="section-foodies" :class="{ '-bordersection': bordersection }">
    <div class="titles">
      <div v-if="subtitle" class="subtitle">{{ subtitle }}</div>

      <div v-if="title" class="title" :class="{ '-smalltitle': smalltitle }">
        {{ title }}
      </div>

      <div v-if="subtitlecenter" class="subtitlecenter">
        {{ subtitlecenter }}
      </div>

      <div
        v-if="titlecenter"
        class="titlecenter"
        :class="{ '-smalltitle': smalltitle }"
      >
        {{ titlecenter }}
      </div>

      <div v-if="description" class="description">{{ description }}</div>

      <div
        class="contentmid"
        :class="{ '-alignleft': alignleft }"
        v-if="contentMid"
      >
        <slot />
      </div>

      <button-foodies
        v-if="actionButton"
        class="action-button"
        :class="{ '-actionbuttonbottom': actionButtonBottom }"
        primary
      >
        {{ actionButtonText }}
      </button-foodies>

      <button-foodies
        v-if="actionButton"
        class="action-button-block"
        :class="{ '-actionbuttonbottom': actionButtonBottom }"
        primary
        block
      >
        {{ actionButtonText }}
      </button-foodies>

      <div class="logo" v-if="logo">
        <img class="imagecontent" src="@/assets/images/logos/logo_1.png" />
        <img class="imagecontent" src="@/assets/images/logos/logo_2.png" />
        <img class="imagecontent" src="@/assets/images/logos/logo_3.png" />
      </div>

      <div
        class="content"
        :class="{ '-alignleft': alignleft, '-columngap': columngap }"
        v-if="!contentMid"
      >
        <slot />
      </div>
    </div>

    <div
      class="illustration"
      :class="{
        '-illustrationbottom': illustrationBottom,
        '-illustrationtop': illustrationTop,
        '-illustrationtopreverse': illustrationTopReverse,
        '-illustrationlarge': illustrationLarge,
        '-illustrationsmall': illustrationSmall,
      }"
      v-if="illustration"
    >
      <img class="image-main" :src="srcImgMain" />
      <img
        class="image-effect"
        src="@/assets/images/polcadot.png"
        v-show="polcadot"
      />

      <div class="ratings" v-show="ratings">
        5.0 Ratings
        <div class="stars">
          <span class="material-symbols-outlined star"> star </span>
          <span class="material-symbols-outlined star"> star </span>
          <span class="material-symbols-outlined star"> star </span>
          <span class="material-symbols-outlined star"> star </span>
          <span class="material-symbols-outlined star"> star </span>
        </div>
      </div>

      <div class="quality" v-show="quality">
        <img class="image-effect" src="@/assets/images/mulher_2.png" />
        Good Quality Product
      </div>
    </div>

    <div class="logobottom" v-if="logo">
      <img class="imagecontent" src="@/assets/images/logos/logo_1.png" />
      <img class="imagecontent" src="@/assets/images/logos/logo_2.png" />
      <img class="imagecontent" src="@/assets/images/logos/logo_3.png" />
    </div>
  </div>
</template>

<script>
import ButtonFoodies from "@/components/ButtonFoodies.vue";

export default {
  name: "SectionFoodies",

  components: {
    ButtonFoodies,
  },

  props: {
    title: {
      type: String,
      default: "",
    },
    smalltitle: {
      type: Boolean,
      default: false,
    },
    subtitle: {
      type: String,
      default: "",
    },
    description: {
      type: String,
      default: "",
    },
    srcImg: {
      type: String,
      default: null,
    },
    actionButton: {
      type: Boolean,
      default: false,
    },
    actionButtonText: {
      type: String,
      default: "",
    },
    actionButtonBottom: {
      type: Boolean,
      default: false,
    },
    illustration: {
      type: Boolean,
      default: false,
    },
    illustrationBottom: {
      type: Boolean,
      default: false,
    },
    illustrationTop: {
      type: Boolean,
      default: false,
    },
    illustrationTopReverse: {
      type: Boolean,
      default: false,
    },
    illustrationLarge: {
      type: Boolean,
      default: false,
    },
    illustrationSmall: {
      type: Boolean,
      default: false,
    },
    polcadot: {
      type: Boolean,
      default: false,
    },
    ratings: {
      type: Boolean,
      default: false,
    },
    quality: {
      type: Boolean,
      default: false,
    },
    alignleft: {
      type: Boolean,
      default: false,
    },
    bordersection: {
      type: Boolean,
      default: false,
    },
    contentMid: {
      type: Boolean,
      default: false,
    },
    logo: {
      type: Boolean,
      default: false,
    },
    titlecenter: {
      type: Boolean,
      default: false,
    },
    subtitlecenter: {
      type: Boolean,
      default: false,
    },
    columngap: {
      type: Boolean,
      default: false,
    },
  },

  data() {
    return {
      srcImgMain: "",
    };
  },

  mounted() {
    if (this.srcImg) {
      this.srcImgMain = require(`@/assets/images/${this.srcImg}`);
    }
  },
};
</script>

<style lang="scss" scoped>
.section-foodies {
  position: relative;
  display: flex;
  flex-direction: column;
  background: none;
  font-family: "Inter";

  $limitdivchild: 6;

  @for $order from 0 through $limitdivchild {
    > *:nth-child(#{$order}) {
      order: calc($order * 10);
    }
  }

  &.-bordersection {
    border-top: 0.1px solid #707070;
    border-bottom: 0.1px solid #707070;
  }

  > .titles {
    > .subtitle {
      margin: 35px 0;
      font-size: 15px;
      font-weight: 500;
      line-height: 18px;
      text-align: center;
    }

    > .title {
      margin-top: 25px;
      margin-bottom: 52px;
      font-size: 51px;
      font-weight: 600;
      line-height: 62px;
      text-align: center;

      &.-smalltitle {
        margin: 0;
        font-size: 35px;
        font-weight: 500;
        line-height: 42px;
      }
    }

    > .subtitlecenter {
      margin: 35px 0;
      font-size: 15px;
      font-weight: 500;
      line-height: 18px;
      text-align: center;
    }

    > .titlecenter {
      margin-top: 25px;
      margin-bottom: 52px;
      font-size: 51px;
      font-weight: 600;
      line-height: 62px;
      text-align: center;

      &.-smalltitle {
        margin: 0;
        font-size: 35px;
        font-weight: 500;
        line-height: 42px;
      }
    }

    > .description {
      margin-top: 25px;
      font-size: 14px;
      font-weight: 400;
      line-height: 22px;
      text-align: center;
    }

    > .content {
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
      justify-content: center;
      // column-gap: 20%;
      // column-gap: 50px;
      margin-top: 45px;
      // margin-bottom: 65px;
      &.-columngap {
        column-gap: 50px;
      }
    }

    > .contentmid {
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
      justify-content: space-evenly;
      column-gap: 20%;
      margin-top: 45px;
    }

    > .action-button {
      display: none;
    }

    > .action-button-block {
      margin-top: 30px;
    }

    > .logo {
      display: none;
    }
  }

  > .logobottom {
    order: 31;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: space-around;
  }

  > .illustration {
    &.-illustrationbottom {
      position: relative;
      // margin-top: 47px;
      margin-bottom: 10%;
      align-self: center;

      > .image-main {
        max-width: 100%;
      }

      > .image-effect {
        position: absolute;
        width: 44%;

        bottom: 0;
        right: 0;
      }

      > .ratings {
        position: absolute;
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: center;
        column-gap: 10px;
        width: 230px;
        height: 53px;

        bottom: 15%;
        right: 10%;

        background: #fff;

        font-size: 15px;
        font-weight: 500;

        border-radius: 25px;

        > .stars {
          color: #06c167;
        }
      }

      > .quality {
        position: absolute;
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: center;
        column-gap: 20px;
        width: 230px;
        height: 53px;

        bottom: 0;
        right: 10%;

        background: #fff;

        font-size: 15px;
        font-weight: 500;

        border-radius: 25px;

        box-shadow: 0px 4px 13px rgba(0, 0, 0, 0.1);
      }
    }

    &.-illustrationtop {
      display: flex;
      justify-content: center;
      width: max-content;
      padding: 0 20px;
      margin-top: 65px;
      margin-bottom: 35px;
      align-self: center;
      background: #f0f1ec;
      order: -1;

      > .image-main {
        max-width: 100%;
        max-height: 100%;
        width: 280px;
        transform: translateY(-6%);
      }

      &.-illustrationlarge {
        height: 380px;
      }

      &.-illustrationsmall {
        height: 400px;
      }
    }
  }

  // > .content {
  //   display: flex;
  //   flex-direction: row;
  //   flex-wrap: wrap;
  //   justify-content: space-evenly;
  //   column-gap: 20%;
  //   margin-top: 52px;
  // }
}

@media screen and (min-width: 768px) {
  .section-foodies {
    display: grid;
    grid-auto-flow: column;

    > .titles {
      margin-top: 20px;
      // margin-left: 84px;
      // margin-right: 80px;

      > .title {
        margin-bottom: 0;
        text-align: left;

        &.-smalltitle {
          margin: 0;
          font-size: 35px;
          font-weight: 500;
          line-height: 42px;
        }
      }

      > .description {
        text-align: left;
        font-size: 14px;
        font-weight: 400;
        line-height: 22px;
      }

      > .subtitle {
        margin-top: 50px;
        text-align: left;
        font-size: 15px;
        font-weight: 500;
        line-height: 18px;
      }

      > .titlecenter {
        text-align: center;
        margin-bottom: 0;

        &.-smalltitle {
          margin: 0;
          font-size: 35px;
          font-weight: 500;
          line-height: 42px;
        }
      }

      > .subtitlecenter {
        text-align: center;
        margin-top: 50px;
        font-size: 15px;
        font-weight: 500;
        line-height: 18px;
      }

      > .content {
        margin-bottom: 65px;

        &.-alignleft {
          justify-content: flex-start;
        }
      }

      > .action-button-block {
        display: none;
      }

      > .action-button {
        display: initial;

        margin-top: 30px;
      }

      > .logo {
        order: 31;
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: space-around;
        margin-top: 100px;
      }
    }

    > .logobottom {
      display: none;
    }

    > .illustration {
      &.-illustrationbottom {
        position: relative;
        width: 100%;
        margin-top: 0;

        > .image-main {
          // margin-right: 100px;
        }

        > .ratings {
          > .stars {
            color: #06c167;
          }
        }

        > .quality {
          position: absolute;
          display: flex;
          flex-direction: row;
          align-items: center;
          justify-content: center;
          column-gap: 20px;
          width: 230px;
          height: 53px;

          bottom: 0;
          right: 10%;

          background: #fff;

          font-size: 15px;
          font-weight: 500;

          border-radius: 25px;

          box-shadow: 0px 4px 13px rgba(0, 0, 0, 0.1);
        }
      }

      &.-illustrationtop {
        > .image-main {
          width: auto;
        }
      }

      &.-illustrationtopreverse {
        justify-self: self-end;

        > .image-main {
          width: auto;
        }

        order: 11;
      }
    }
  }
}
</style>
