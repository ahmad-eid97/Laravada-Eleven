<template>
  <section class="intro">
    <VueSlickCarousel
      :slidesToShow="1"
      :slidesToScroll="1"
      :arrows="true"
      :fade="true"
      :dots="false"
    >
      <div
        class="item item-1"
        v-for="slide in slides"
        :key="slide.id"
        :style="{ background: `url(${slide.background})` }"
      >
        <div class="overlay"></div>
        <div class="row m-0 justify-content-center align-items-center h-100">
          <div class="content">
            <h2>
              {{ slide.title }}
            </h2>
            <p>
              {{ slide.description }}
            </p>
            <a :href="slide.link" class="btn">LEARN MORE</a>
          </div>
        </div>
      </div>
    </VueSlickCarousel>
  </section>
</template>

<script>
import VueSlickCarousel from "vue-slick-carousel";
import "vue-slick-carousel/dist/vue-slick-carousel.css";
import "vue-slick-carousel/dist/vue-slick-carousel-theme.css";
export default {
  components: { VueSlickCarousel },
  name: "AppHomeSlider",
  props: ["slides"],
};
</script>

<style lang="scss">
.intro {
  margin-top: 130px;
}
.intro .item {
  min-height: 500px;
  background-size: cover !important;
  background-repeat: no-repeat;
  background-position: center;
  position: relative;
}
.intro .item .overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 0;
  background-color: rgba(0, 0, 0, 0.51);
}
.intro .item .row {
  min-height: 500px;
}
.intro .item .content {
  position: relative;
  z-index: 1;
  text-align: center;
  max-width: 800px;
}
.intro .item .content h1 {
  color: rgb(255, 255, 255);
  font-size: 100px;
  font-weight: 700;
  line-height: 150px;
}
.intro .item .content h2 {
  color: rgb(255, 255, 255);
  font-size: 50px;
  font-weight: 700;
  line-height: 60px;
  text-transform: uppercase;
  visibility: visible;
  z-index: 1;
  text-align: center;
}
.intro .item .content p {
  color: rgb(255, 255, 255);
  font-size: 24px;
  font-weight: 500;
  /* height: 68px; */
  line-height: 34px;
  position: relative;
  text-align: center;
}
@include sm {
  .intro .item .content h2 {
    font-size: 35px;
    line-height: 50px;
  }
  .intro .item .content p {
    font-size: 18px;
    line-height: 24px;
  }
}
.intro .item .content .btn {
  background-color: rgb(117, 179, 37);
  border-radius: 3px;
  border: none;
  color: rgb(255, 255, 255);
  cursor: pointer;
  font-size: 20px;
  font-weight: 700;
  height: 50px;
  line-height: 20px;
  padding-bottom: 15px;
  padding-left: 35px;
  padding-right: 35px;
  padding-top: 15px;
}
.intro .content .btn:hover {
  color: rgb(117, 179, 37);
  background-color: rgb(255, 255, 255);
}
.intro .slick-prev {
  left: 0px;
}
.intro .slick-next {
  right: 10px !important;
}
.intro .slick-prev,
.intro .slick-next {
  width: 40px;
  height: 40px;
  z-index: 2;
}
.intro .slick-prev::before,
.intro .slick-next::before {
  font-family: "slick";
  font-size: 30px;
  line-height: 1;
  opacity: 0.75;
  /* color: #020606; */
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
