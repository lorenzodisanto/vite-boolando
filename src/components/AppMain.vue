<script>
import { store } from "../store";
import AppCard from "./AppCard.vue";
import axios from "axios";

export default {
  data() {
    return {
      store,
      products: [],
    };
  },

  methods: {
    buildImagePath(imageName) {
      const imageUrl = new URL("../assets/img/" + imageName, import.meta.url);
      return imageUrl.href;
    },

    handleCardOpen(productIndex) {
      const selectProduct = this.products[productIndex];
      store.modal.title = selectProduct.brand;
      store.modal.price = selectProduct.price;
      store.modal.description = selectProduct.name;
      store.modal.show = true;
    },
  },

  components: { AppCard },

  created() {
    axios.get(`${store.apiUri}/products`).then((res) => {
      this.products = res.data;
    });
  },
};
</script>

<template>
  <main>
    <div class="container products">
      <app-card
        v-for="(product, index) in products"
        :index="index"
        :imgFront="buildImagePath(product.frontImage)"
        :imgBack="buildImagePath(product.backImage)"
        :titleBrand="product.brand"
        :titleName="product.name"
        :oldPrice="product.price"
        :prodBadges="product.badges"
        @card-open="handleCardOpen"
      ></app-card>
    </div>
  </main>
</template>

<style lang="scss" scoped>
.products {
  flex-wrap: wrap;
  justify-content: center;
  margin-top: 50px;
}
</style>
