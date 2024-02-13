<script>
import { store } from "./store";

import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
import AppFooter from "./components/AppFooter.vue";
import AppModal from "./components/AppModal.vue";

export default {
  data() {
    return {
      title: "Vite Boolando",
      store,
      genders: [
        {
          text: "Donna",
          url: "#",
          current: false,
        },
        {
          text: "Uomo",
          url: "#",
          current: false,
        },
        {
          text: "Bambini",
          url: "#",
          current: false,
        },
      ],

      footerInfo: [
        {
          text: "Informazioni legali",
          url: "#",
          current: false,
        },
        {
          text: "Informativa sulla privacy",
          url: "#",
          current: false,
        },
        {
          text: "Diritto di recesso",
          url: "#",
          current: false,
        },
      ],
    };
  },

  components: { AppHeader, AppMain, AppFooter, AppModal },
};
</script>

<template>
  <app-header :links="genders"></app-header>
  <app-modal v-if="store.modal.show"></app-modal>
  <app-main></app-main>
  <app-footer :infos="footerInfo"></app-footer>
</template>

<style lang="scss">
@use "./styles/general.scss";
</style>
