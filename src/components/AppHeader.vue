<script>
export default {
  props: {
    links: Array,
  },
};
</script>

<template>
  <header>
    <div class="container">
      <div>
        <ul>
          <li v-for="link in links">
            <a :href="link.url">{{ link.text }}</a>
          </li>
        </ul>
      </div>
      <div>
        <img src="../assets/img/boolean-logo.png" alt="" />
      </div>
      <div>
        <ul>
          <li>
            <a href="#"><i class="fa-regular fa-user"></i></a>
          </li>
          <li>
            <a href="#"><i class="fa-regular fa-heart"></i></a>
          </li>
          <li>
            <a href="#"><i class="fa-solid fa-bag-shopping"></i></a>
          </li>
        </ul>
      </div>
    </div>
  </header>
</template>

<style lang="scss" scoped>
header {
  min-height: 75px;
  background-color: #ff6900;
  box-shadow: 0px 2px 3px 0px #555;
  position: sticky;
  top: 0;
  z-index: 3;

  .container {
    min-height: 75px;
  }

  a {
    color: white;
  }

  img {
    width: 150px;
  }
}
</style>
