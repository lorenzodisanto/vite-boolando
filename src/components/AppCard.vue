<script>
export default {
  props: {
    imgFront: String,
    imgBack: String,
    titleBrand: String,
    titleName: String,
    oldPrice: Number,
    prodBadges: Array,
  },
};
</script>

<template>
  <div class="card">
    <img :src="imgFront" alt="" />
    <img :src="imgBack" alt="" class="second-img" />
    <p class="sale" v-for="prodBadge in prodBadges">
      <span class="red" v-if="prodBadge.type == 'discount'">{{
        prodBadge.value
      }}</span>
      <span class="green" v-if="prodBadge.type == 'tag'">{{
        prodBadge.value
      }}</span>
    </p>
    <p class="heart">&hearts;</p>
    <div class="description">
      <p>{{ titleBrand }}</p>
      <h4>{{ titleName }}</h4>
      <p>
        <span class="bold">{{ oldPrice }}</span>
        <!-- <span class="throught">{{ oldPrice }}</span> -->
      </p>
    </div>
  </div>
</template>

<style lang="scss" scope>
.card {
  width: calc(100% / 3 - 10px);
  margin: 5px;
  min-width: 350px;
  margin-top: 40px;
  position: relative;
}

.card img {
  margin: 0 auto;
  display: block;
  width: 100%;
  position: relative;
  z-index: 1;
}

.sale {
  position: absolute;
  left: 0;
  bottom: 90px;
  color: white;
  font-size: 1rem;
  z-index: 2;
}

.description .bold {
  color: red;
  font-weight: bold;
}

.throught {
  text-decoration: line-through;
}

.red {
  background-color: red;
  margin: 3px;
  margin-left: 0;
  padding: 3px 7px;
}

.green {
  background-color: green;
  margin-left: 60px;
  padding: 3px 7px;
}

.heart {
  position: absolute;
  right: 0;
  top: 10px;
  background-color: white;
  font-size: 2rem;
  padding: 5px 12px;
  z-index: 2;
}

.heart:hover {
  color: red;
}

.card .second-img {
  position: absolute;
  top: 0;
  z-index: 0;
}

.card:hover .second-img {
  z-index: 1;
}
</style>
