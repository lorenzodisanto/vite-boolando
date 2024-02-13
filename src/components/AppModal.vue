<script>
import { store } from "../store";

export default {
  data() {
    return {
      store,
    };
  },

  methods: {
    closeModal() {
      store.modal.show = false;
    },
  },
};
</script>

<template>
  <div class="layover">
    <div class="modal">
      <i
        class="fa-solid fa-square-xmark fa-xl close-modal"
        @click="closeModal()"
      ></i>
      <h3>{{ store.modal.title }}</h3>
      <h4>
        {{ store.modal.description }}
      </h4>
      <h4>{{ store.modal.price }} €</h4>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.layover {
  position: fixed;
  z-index: 3;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  background-color: rgba(0, 0, 0, 0.6);

  .modal {
    width: 30%;
    background-color: white;
    border-radius: 10px;
    padding: 15px;
    position: relative;

    .close-modal {
      position: absolute;
      top: 25px;
      right: 15px;
      cursor: pointer;
    }
  }
}
</style>
