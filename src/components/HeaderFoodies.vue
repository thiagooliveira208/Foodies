<template>
  <div class="header-foodies">
    <h1 class="title">Foodies</h1>
    <div class="menu">
      <span class="material-symbols-outlined menubar"> menu </span>
    </div>

    <ul class="menulist">
      <li class="menuoption">Home <span class="menupointer">•</span></li>
      <li class="menuoption">About Us</li>
      <li class="menuoption">Service Us</li>
      <li class="menuoption">Our Company</li>
      <li class="menuoption">Pages</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HeaderFoodies",
};
</script>

<style lang="scss" scoped>
.header-foodies {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  height: 86px;

  background: #f3fcf7;

  > .title {
    padding: 25px 0;

    font-family: "Inter";
    font-size: 32px;
    font-weight: 500;
    color: #06c167;
  }

  > .menu {
    width: 47px;
    height: 39px;
    align-self: center;
    text-align: center;

    color: #06c167;

    border: 2px solid #06c167;

    > .menubar {
      padding-top: 3px;
      font-size: 32px;
    }
  }

  > .menulist {
    display: none;
  }
}

@media screen and (min-width: 768px) {
  .header-foodies {
    > .menu {
      display: none;
    }

    > .menulist {
      display: flex;
      column-gap: 44px;
      margin-top: 30px;

      font-family: "Inter";
      font-weight: 400;
      font-size: 16px;
      line-height: 19px;
      color: #1d1d1f;

      > .menuoption {
        cursor: pointer;

        > .menupointer {
          display: flex;
          justify-content: center;
        }
      }

      > .menuoption:hover {
        color: #06c167;
      }
    }
  }
}
</style>
