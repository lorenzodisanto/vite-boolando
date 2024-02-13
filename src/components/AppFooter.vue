<script>
export default {
  props: {
    infos: Array,
  },
};
</script>

<template>
  <footer>
    <div class="container footer-container">
      <div class="footer-left">
        <h3>Boolando s.r.l</h3>
        <ul>
          <li v-for="info in infos">
            <a :href="info.url">{{ info.text }}</a>
          </li>
        </ul>
      </div>
      <div class="footer-right">
        <h6>Trovaci anche su</h6>
        <i class="fa-brands fa-square-twitter"></i>
        <i class="fa-brands fa-square-facebook"></i>
        <i class="fa-brands fa-square-instagram"></i>
        <i class="fa-brands fa-square-pinterest"></i>
        <i class="fa-brands fa-square-youtube"></i>
      </div>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
footer {
  min-height: 90px;
  margin-top: 60px;
  background-color: #1a1a1a;
  color: white;
  display: flex;

  .footer-container {
    width: 100%;
    align-items: center;
  }

  .footer-left {
    width: 90%;
    line-height: 30px;
    align-items: center;
  }
  .footer-left a {
    margin-left: 0;
  }

  .footer-right {
    width: 10%;
    font-size: 1.3rem;
    line-height: 30px;

    i {
      margin-left: 5px;
    }
  }
}
</style>
