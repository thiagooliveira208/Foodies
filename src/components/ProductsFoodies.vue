<template>
  <div class="products-foodies">
    <img class="imagefood" :src="srcImgMain" />

    <div class="stars">
      <span class="material-symbols-outlined star"> star </span>
      <span class="material-symbols-outlined star"> star </span>
      <span class="material-symbols-outlined star"> star </span>
      <span class="material-symbols-outlined star"> star </span>
      <span class="material-symbols-outlined star"> star </span>
    </div>

    <div class="textcontent">
      <div class="description">
        {{ description }}
      </div>

      <span class="oldPrice">${{ oldPrice }}</span>
      <span class="price">${{ price }}</span>

      <button-foodies
        v-if="actionButton"
        class="action-button"
        primary
        outline
        small
      >
        {{ actionButtonText }}
      </button-foodies>
    </div>
  </div>
</template>

<script>
import ButtonFoodies from "@/components/ButtonFoodies.vue";

export default {
  name: "ProductsFoodies",

  components: {
    ButtonFoodies,
  },

  props: {
    description: {
      type: String,
      default: "",
    },
    price: {
      type: String,
      default: "",
    },
    oldPrice: {
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
.products-foodies {
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 445px;
  width: 100%;
  max-width: 320px;
  margin-bottom: 35px;

  font-family: "Inter";

  border: 2px solid rgba(118, 118, 117, 0.25);

  > .imagefood {
    margin: 25px;
  }

  > .stars {
    color: #06c167;
  }

  > .textcontent {
    text-align: center;

    > .description {
      margin: 18px 0;
      font-size: 20px;
      font-weight: 400;
      line-height: 24px;
      color: #1d1d1f;
    }

    > .oldPrice {
      padding-right: 10px;
      font-size: 20px;
      font-weight: 600;
      line-height: 24px;
      color: #767675;
      text-decoration-line: line-through;
      opacity: 0.35;
    }

    > .price {
      font-size: 20px;
      font-weight: 400;
      line-height: 24px;
      color: #06c167;
    }

    > .action-button {
      width: 100%;
      margin-top: 15%;
    }
  }
}

@media (min-width: 769px) {
  .products-foodies {
    max-width: 270px;
    max-height: 445px;
    margin: 5px 12px;
  }
}
</style>
