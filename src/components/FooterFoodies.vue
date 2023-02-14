<template>
  <div class="footer-foodies">
    <div class="footercontents">
      <div class="brand">
        <h2 class="titlebrand">Foodies</h2>

        <p class="descriptionbrand">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Odio ab nulla
          quisquam
        </p>

        <img class="social" :src="facebook" />
        <img class="social" :src="instagram" />
        <img class="social" :src="twitter" />
      </div>

      <div class="menu">
        <h3 class="titlemenu">About Us</h3>

        <p class="optionmenu">About Us</p>
        <p class="optionmenu">Service Us</p>
        <p class="optionmenu">Contact</p>
        <p class="optionmenu">Company</p>
      </div>

      <div class="menu">
        <h3 class="titlemenu">Company</h3>

        <p class="optionmenu">Partnership</p>
        <p class="optionmenu">Terms of Use</p>
        <p class="optionmenu">Privacy</p>
        <p class="optionmenu">Sitemap</p>
      </div>

      <div class="subscribe">
        <h3 class="titlesubscribe">Get in touch</h3>

        <p class="descriptionsubscribe">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Commodi at,
          soluta.
        </p>

        <input class="emailsubscribe" type="email" placeholder="Email" />

        <button-foodies v-if="actionButton" class="actionbutton" primary block>
          Subscribe
        </button-foodies>
      </div>
    </div>

    <p class="copyright">Copyright 2021 Foodies.</p>
  </div>
</template>

<script>
import ButtonFoodies from "@/components/ButtonFoodies.vue";
import facebook from "@/assets/images/social/facebook.png";
import instagram from "@/assets/images/social/instagram.png";
import twitter from "@/assets/images/social/twitter.png";

export default {
  name: "FooterFoodies",

  components: {
    ButtonFoodies,
  },

  data() {
    return {
      facebook,
      instagram,
      twitter,
    };
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
  },
};
</script>

<style lang="scss" scoped>
.footer-foodies {
  > .footercontents {
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    text-align: center;

    height: 1291px;

    font-family: "Inter";

    > .brand {
      > .titlebrand {
        padding: 10px;
        font-size: 32px;
        font-weight: 500;
        line-height: 39px;
        color: #06c167;
      }

      > .descriptionbrand {
        padding: 15px;
        font-size: 16px;
        font-weight: 400;
        line-height: 29px;
        color: #1d1d1f;
      }

      > .social {
        padding: 10px 12px;
      }
    }

    > .menu {
      > .titlemenu {
        margin-bottom: 28px;
        font-size: 24px;
        font-weight: 500;
        line-height: 29.05px;
        color: #1d1d1f;
      }

      > .optionmenu {
        padding: 7px 0;
        font-size: 16px;
        font-weight: 400;
        line-height: 19.36px;
        color: #1d1d1f;
      }
    }

    > .subscribe {
      > .titlesubscribe {
        font-size: 24px;
        font-weight: 500;
        line-height: 29.05px;
        color: #1d1d1f;
      }

      > .descriptionsubscribe {
        padding: 20px 0;
        font-size: 16px;
        font-weight: 400;
        line-height: 19.36px;
        color: #1d1d1f;
      }

      > .emailsubscribe {
        box-sizing: border-box;
        height: 68px;
        width: 100%;
        margin-bottom: 5px;
        text-align: center;
        border: none;
        background: #f0f1ec;
        color: #394149;
      }

      > .actionbutton {
        max-width: 100%;
      }
    }
  }

  .copyright {
    margin-top: 100px;
    max-width: 100%;
    width: 100vw;
    text-align: center;

    font-size: 16px;
    font-weight: 400;
    line-height: 19px;
    color: #1d1d1f;
  }
}

@media screen and (min-width: 768px) {
  .footer-foodies {
    > .footercontents {
      display: grid;
      grid-template-columns: 1fr 1fr 1fr 2fr;
      height: max-content;

      margin-top: 140px;

      align-items: left;
      text-align: left;

      > .brand {
        width: 450px;

        > .descriptionbrand {
          padding-right: 150px;
        }
      }

      > .subscribe {
        display: grid;
        grid-template-columns: 65% 30%;
        grid-template-rows: auto auto auto;
        grid-column-gap: 5%;

        > .titlesubscribe {
          grid-column: 2 span;
          font-size: 24px;
          font-weight: 500;
          line-height: 29.05px;
          color: #1d1d1f;
        }

        > .descriptionsubscribe {
          grid-column: 2 span;
          padding: 7% 0;
          font-size: 16px;
          font-weight: 400;
          line-height: 19.36px;
          color: #1d1d1f;
        }

        > .emailsubscribe {
          width: 80%;
          box-sizing: border-box;
          height: 68px;
          width: 100%;
          margin-bottom: 5px;
          text-align: center;
          border: none;
          background: #f0f1ec;
          color: #394149;
        }

        > .actionbutton {
          max-width: max-content;
        }
      }
    }
  }
}
</style>
