<template>
  <section class="news">
    <div class="row m-0">
      <h2>What's new at Seven Weed</h2>
    </div>

    <swiper :options="swiperOption">
      <swiper-slide v-for="blog in blogs" :key="blog.id">
        <div>
          <div class="item">
            <div class="image">
              <img class="img-fluid" :src="blog.image" alt="" />
              <span class="date">
                <span class="d-inline-block month">
                  {{ $date(new Date(blog.publish_date), "dd") }}
                </span>
                <span class="d-block day">
                  {{ $date(new Date(blog.publish_date), "MMM") }}
                </span>
              </span>
              <span class="tag"> {{ blog.category.name }} </span>
            </div>
            <h3>
              <a href="#"> {{ blog.title }} </a>
            </h3>
            <p>
              {{ blog.short_description }}
            </p>
            <nuxt-link :to="`/blog/${blog.id}`" class="btn">
              Read more
              <i class="fa-solid fa-caret-right"></i>
            </nuxt-link>
          </div>
        </div>
      </swiper-slide>
    </swiper>
    <div class="blogsBtn">
      <button @click="$router.push('/blogs')">See All Blogs</button>
    </div>
  </section>
</template>

<script>
export default {
  name: "AppHomeNews",
  props: ["blogs"],
  data() {
    return {
      swiperOption: {
        loop: true,
        slidesPerView: 3,
        spaceBetween: 50,
        breakpoints: {
          // when window width is >= 320px
          100: {
            slidesPerView: 1,
            spaceBetween: 5,
          },
          // when window width is >= 480px
          480: {
            slidesPerView: 1,
            spaceBetween: 5,
          },
          // when window width is >= 640px
          640: {
            slidesPerView: 1,
            spaceBetween: 5,
          },
          992: {
            slidesPerView: 2,
            spaceBetween: 5,
          },
          1200: {
            slidesPerView: 3,
            spaceBetween: 5,
          },
        },
      },
    };
  },
};
</script>

<style lang="scss">
.news {
  padding: 80px 50px 70px;
  background-size: cover;
  background-color: rgba(0, 0, 0, 0);
  background-image: url("https://the7.io/weed/wp-content/uploads/sites/51/2019/01/w002.jpg");
  background-attachment: fixed;
}
@include sm {
  .news {
    padding: 50px 10px;
  }
}
.news h2 {
  color: rgb(255, 255, 255);
  font-size: 34px;
  font-weight: 700;
  line-height: 44px;
  text-align: center;
  margin-bottom: 70px;
}
.news .item {
  background-color: #fff;
  padding: 30px;
  max-width: 380px;
  margin: 0 auto;
}
.news .item .image {
  max-width: 320px;
  height: 240px;
  overflow: hidden;
  position: relative;
  margin-bottom: 20px;
}
.news .item .image img {
  transition: all 2s linear;
}
.news .item .image:hover img {
  transform: scale(1.2);
}
.news .item .image .date {
  position: absolute;
  width: 63px;
  height: 63px;
  background-color: #fff;
  border-radius: 50%;
  top: 10px;
  right: 10px;
  text-align: center;
}
.news .item .image .date .month {
  color: rgb(34, 34, 34);
  font-size: 11px;
  font-weight: 700;
  line-height: 19px;
  margin-bottom: 2px;
  position: relative;
  text-transform: uppercase;
  border-bottom: 2px solid var(--main-color);
}
.blogsBtn {
  display: flex;
  justify-content: center;
  button {
    margin-top: 50px;
    background-color: var(--main-color);
    border-radius: 3px;
    border: none;
    color: rgb(255, 255, 255);
    cursor: pointer;
    font-size: 1rem;
    font-weight: 700;
    height: 50px;
    line-height: 20px;
    padding-bottom: 15px;
    padding-left: 35px;
    padding-right: 35px;
    padding-top: 15px;
    border: 1px solid var(--main-color);
    &:hover {
      background: #fff;
      color: var(--main-color);
    }
  }
}
.news .item .image .date .day {
  color: rgb(34, 34, 34);
  font-size: 24px;
  font-weight: 700;
  line-height: 29px;
}
.news .item .image .tag {
  background-color: rgba(0, 0, 0, 0.75);
  color: rgb(255, 255, 255);
  font-size: 12px;
  font-weight: 700;
  line-height: 22px;
  margin-bottom: 2px;
  margin-left: 0px;
  margin-right: 0px;
  margin-top: 0px;
  padding-bottom: 1px;
  padding-left: 9px;
  padding-right: 9px;
  padding-top: 2px;
  position: absolute;
  top: 10px;
  left: 10px;
}
.news .item h3 a {
  color: rgb(51, 51, 51);
  font-size: 20px;
  font-weight: 700;
  text-decoration-line: none;
  transition-delay: 0s;
  transition-duration: 0.35s;
  transition-property: color;
  transition-timing-function: ease;
  text-transform: uppercase;
}
.news .item h3 a:hover {
  color: rgb(117, 179, 37);
}
.news .item p {
  color: rgb(133, 134, 140);
  font-size: 14px;
  line-height: 21px;
  margin-bottom: 10px;
}
.news .item .btn {
  background-color: var(--main-color);
  border-radius: 3px;
  border: none;
  color: rgb(255, 255, 255);
  cursor: pointer;
  font-size: 12px;
  font-weight: 700;
  line-height: 14px;
  padding-bottom: 8px;
  padding-left: 12px;
  padding-right: 12px;
  padding-top: 8px;
  margin-bottom: 20px;
  margin-left: 0px;
  margin-right: 10px;
  margin-top: 0px;
}
.news .item .btn:hover {
  background-color: rgb(160, 209, 95);
  color: rgb(255, 255, 255);
  box-shadow: rgba(0, 0, 0, 0.25) 0px 4px 13px 2px;
}
.news .slick-prev {
  left: -25px;
}
.news .slick-next {
  right: -25px;
}
.news .slick-prev,
.news .slick-next {
  width: 40px;
  height: 40px;
  z-index: 2;
}
.news .slick-prev::before,
.news .slick-next::before {
  font-family: "slick";
  font-size: 40px;
  line-height: 1;
  opacity: 0.75;
  color: var(--main-color);
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
