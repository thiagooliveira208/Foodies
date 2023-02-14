<template>
  <div id="app">
    <div class="background"></div>

    <header-foodies />

    <section-foodies
      title="We're Serious For Food."
      description="We strive to provide a space where guests can connect with themselves and explore their full potential, offering a safe place."
      action-button
      action-button-text="Get Started"
      illustration
      illustration-bottom
      polcadot
      ratings
      quality
      src-img="mulher_1.png"
      logo
    >
      <!-- <img class="imagecontent" src="@/assets/images/logos/logo_1.png" />
      <img class="imagecontent" src="@/assets/images/logos/logo_2.png" />
      <img class="imagecontent" src="@/assets/images/logos/logo_3.png" /> -->
    </section-foodies>

    <section-foodies bordersection columngap>
      <div class="item">
        <span class="material-symbols-outlined iconbenefits">
          local_shipping
        </span>
        <span class="title"> Free Shipping </span>
        <span class="subtitle"> Orders over $140 </span>
      </div>

      <div class="item">
        <span class="material-symbols-outlined iconbenefits"> wallet </span>
        <span class="title"> Quick Payment </span>
        <span class="subtitle"> 100% secure payment </span>
      </div>

      <div class="item">
        <span class="material-symbols-outlined iconbenefits"> percent </span>
        <span class="title"> Special Promo </span>
        <span class="subtitle"> Get special promo </span>
      </div>

      <div class="item">
        <span class="material-symbols-outlined iconbenefits">
          headset_mic
        </span>
        <span class="title"> 24/7 Support </span>
        <span class="subtitle"> Ready support </span>
      </div>
    </section-foodies>

    <section-foodies
      illustration
      illustration-top
      illustration-large
      alignleft
      src-img="food/saladas_legumes_verde.png"
      subtitle="Our Benefit"
      title="The More Healthy Food The Better"
      smalltitle
    >
      <ul class="listBenefit">
        <li>
          <span class="material-symbols-outlined"> check_small </span>
          Be Alive With Veggie Food.
        </li>
        <li>
          <span class="material-symbols-outlined"> check_small </span>
          It's The Place To Be.
        </li>
        <li>
          <span class="material-symbols-outlined"> check_small </span>
          Nonstop Veggie Food
        </li>
        <li>
          <span class="material-symbols-outlined"> check_small </span>
          The Best Silk Dish In Town
        </li>
        <li>
          <span class="material-symbols-outlined"> check_small </span>
          Truffles, Egg & Pumpkin Spice
        </li>
      </ul>
    </section-foodies>

    <section-foodies
      illustration
      illustration-top
      illustration-top-reverse
      illustration-large
      src-img="food/suco_verde.png"
      subtitle="Our Stars"
      title="Veggie Food Goes On And Always On"
      smalltitle
      action-button
      action-button-text="Get Special Promo"
      action-button-bottom
      content-mid
    >
      <div class="qualificationcontent">
        <div class="textcontent">
          <p class="qualificationtitle">1,500</p>
          <p class="qualificationsubtitle">Sold Product</p>
        </div>
        <div class="textcontent">
          <p class="qualificationtitle">500</p>
          <p class="qualificationsubtitle">Possitive Feedback</p>
        </div>
        <div class="textcontent">
          <p class="qualificationtitle">400</p>
          <p class="qualificationsubtitle">Official Store</p>
        </div>
      </div>
    </section-foodies>

    <section-foodies
      subtitlecenter="Our Features"
      titlecenter="Variety Of Veggie Foods"
      smalltitle
    >
      <content-variety-foodies
        title="Veggies Are Forever"
        description="We offer the following services"
        src-img="food/legumes-fundo-preto.png"
        action-button
        action-button-text="Discover Now"
      />

      <content-variety-foodies
        title="Good For Your Skin"
        description="We offer the following services"
        src-img="food/mamao_2.png"
        action-button
        action-button-text="Discover Now"
      />

      <content-variety-foodies
        title="Veggie Food Groove"
        description="We offer the following services"
        src-img="food/vegetais_variados.png"
        action-button
        action-button-text="Discover Now"
      />

      <content-variety-foodies
        title="That Comes Close"
        description="We offer the following services"
        src-img="food/limao.png"
        action-button
        action-button-text="Discover Now"
      />
    </section-foodies>

    <section-foodies
      subtitlecenter="Our Product"
      titlecenter="Most Popular Product"
      smalltitle
    >
      <products-foodies
        description="Summer Veganie"
        price="29"
        old-price="25"
        src-img="food/banana.png"
        action-button
        action-button-text="Buy Now"
      />

      <products-foodies
        description="Greanie Seafood"
        price="29"
        old-price="25"
        src-img="food/mamao.png"
        action-button
        action-button-text="Buy Now"
      />

      <products-foodies
        description="Fresh Vegetable"
        price="29"
        old-price="25"
        src-img="food/abacate.png"
        action-button
        action-button-text="Buy Now"
      />

      <products-foodies
        description="Fresh Meatyus"
        price="29"
        old-price="25"
        src-img="food/tangerina.png"
        action-button
        action-button-text="Buy Now"
      />
    </section-foodies>

    <section-full-background-foodies
      description="Veggie Foods? Ingredients You Want To Try"
      action-button
      action-button-text="Get Started"
    >
    </section-full-background-foodies>

    <footer-foodies action-button> </footer-foodies>
  </div>
</template>

<script>
import HeaderFoodies from "@/components/HeaderFoodies.vue";
import SectionFoodies from "@/components/SectionFoodies.vue";
import ContentVarietyFoodies from "@/components/ContentVarietyFoodies.vue";
import ProductsFoodies from "@/components/ProductsFoodies.vue";
import SectionFullBackgroundFoodies from "@/components/SectionFullBackgroundFoodies.vue";
import FooterFoodies from "@/components/FooterFoodies.vue";

export default {
  name: "App",
  components: {
    HeaderFoodies,
    SectionFoodies,
    ContentVarietyFoodies,
    ProductsFoodies,
    SectionFullBackgroundFoodies,
    FooterFoodies,
  },
};
</script>

<style lang="scss">
@import url(https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&family=Lato&display=swap);
@import "@/assets/styles/all.scss";

#app {
  margin: 0 30px;
  height: calc(100vh * 10);

  > .background {
    position: absolute;
    top: 0;
    right: 0;
    left: 0;
    height: 932px;
    background: #f3fcf7;
    z-index: -1;
  }
}

.listBenefit {
  li {
    font-weight: 400;
    font-size: 16px;
    line-height: 40px;

    span {
      vertical-align: middle;
      padding-right: 5px;
      font-weight: 700;
      font-size: 40px;
      color: #06c167;
    }
  }
}

.advantages {
  border-bottom: 1.5px solid #ccc;
  border-top: 1.5px solid #ccc;
}

.imagecontent {
  padding-bottom: 40px;
  max-width: 100%;
  width: 126px;
}

.item {
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 220px;
  margin-top: 10px;

  > .iconbenefits {
    padding: 15px 15px;
    margin-bottom: 15px;
    text-align: center;
    color: #06c167;
    background: #f3fcf7;
    font-size: 52px;
    border-radius: 10px;
  }

  > .title {
    padding-top: 5%;

    font-size: 16px;
    font-weight: 400;
  }

  > .subtitle {
    padding-top: 7%;

    font-size: 12px;
    font-weight: 500;
    opacity: 75%;
  }
}

.qualificationcontent {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;

  > .textcontent {
    margin-right: 30px;
    text-align: center;

    > .qualificationtitle {
      margin-top: 8px;
      font-weight: 600;
      font-size: 40px;
      line-height: 48px;

      color: #06c167;
    }

    > .qualificationsubtitle {
      margin-top: 4px;
      margin-bottom: 30px;
      font-weight: 400;
      font-size: 15px;
      line-height: 18px;

      color: #1d1d1f;
      opacity: 0.65;
    }
  }
}

@media (min-width: 769px) {
  #app {
    // margin: 0 50px;

    > .background {
      height: 500px;
    }
  }

  .imagecontent {
    margin-top: 100px;
  }

  .item {
    display: grid;
    grid-template-columns: auto auto;
    grid-template-rows: auto auto;

    height: auto;

    > .iconbenefits {
      grid-row: 2 span;
      padding: 10px 10px;
      margin-bottom: 0;
      margin-right: 10px;

      font-size: 40px;
    }

    > .title {
      width: 100%;
      padding: 0;
      font-family: "Inter";
      font-size: 18px;
      font-weight: 400;
      line-height: 22px;
    }

    > .subtitle {
      width: 100%;
      padding: 0;
      font-family: "Inter";
      font-size: 14px;
      font-weight: 500;
      line-height: 17px;
      opacity: 75%;
    }
  }

  .qualificationcontent {
    display: flex;
    flex-direction: row;
    align-items: center;
    width: 100%;

    > .qualificationtitle {
      margin-top: 8px;
      font-weight: 600;
      font-size: 40px;
      line-height: 48px;

      color: #06c167;
    }

    > .qualificationsubtitle {
      margin-top: 4px;
      margin-bottom: 30px;
      font-weight: 400;
      font-size: 15px;
      line-height: 18px;

      color: #1d1d1f;
      opacity: 0.65;
    }
  }
}
</style>
