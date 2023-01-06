<template>
  <section class="offers">
    <div class="row m-0">
      <h2>Special offers from our online store</h2>
    </div>

    <swiper :options="swiperOption">
      <swiper-slide v-for="product in products" :key="product.id">
        <div>
          <div class="item">
            <div class="image">
              <img class="img-fluid" :src="product.images[0]" alt="" />
            </div>
            <h4>
              {{ product.title }}
            </h4>
            <span class="price"> ${{ product.current_price }} </span>
            <div class="content"></div>
            <button class="btn" @click="addToCart(product)">Add to cart</button>
          </div>
        </div>
      </swiper-slide>
    </swiper>
    <div class="shopBtnWrapper">
      <button class="shopBtn" @click="$router.push('/our-shop')">
        Visit Our Shop
      </button>
    </div>
  </section>
</template>

<script>
export default {
  name: "AppHomeOffers",
  props: ["products"],
  data() {
    return {
      swiperOption: {
        loop: true,
        slidesPerView: 5,
        spaceBetween: 50,
        breakpoints: {
          // when window width is >= 320px
          100: {
            slidesPerView: 1,
            spaceBetween: 5,
          },
          // when window width is >= 480px
          480: {
            slidesPerView: 2,
            spaceBetween: 5,
          },
          // when window width is >= 640px
          640: {
            slidesPerView: 3,
            spaceBetween: 5,
          },
          992: {
            slidesPerView: 4,
            spaceBetween: 5,
          },
          1200: {
            slidesPerView: 5,
            spaceBetween: 5,
          },
        },
      },
    };
  },
  methods: {
    addToCart(product) {
      const item = {
        id: product.id,
        images: product.images,
        title: product.title,
        current_price: product.current_price,
        quantity: 1,
      };
      let cartItems = localStorage.getItem("laravadaCart")
        ? JSON.parse(localStorage.getItem("laravadaCart"))
        : [];

      let aleradyExists = cartItems.find((one) => one.id === item.id);
      if (aleradyExists) {
        aleradyExists.quantity = aleradyExists.quantity + 1;
      } else {
        cartItems.unshift(item);
      }
      this.$store.state.cartItems = cartItems;
      localStorage.setItem("laravadaCart", JSON.stringify(cartItems));
      this.$toast.success("Product added to cart successfully");
    },
  },
};
</script>

<style>
.offers {
  padding: 70px 50px;
}
.offers h2 {
  color: rgb(51, 51, 51);
  font-size: 34px;
  font-weight: 700;
  line-height: 44px;
  text-align: center;
  padding: 0 25px 70px;
}
.image {
  height: 250px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.image img {
  height: 100%;
}
.offers h4 {
  color: rgb(51, 51, 51);
  font-size: 15px;
  margin-top: 15px;
  text-align: center;
}
.offers .price {
  color: rgb(51, 51, 51);
  display: block;
  font-size: 15px;
  margin-top: 5px;
  text-align: center;
}
.shopBtnWrapper {
  display: flex;
  justify-content: center;
}
.shopBtn {
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
  margin: auto;
}
.shopBtn:hover {
  background: #fff;
  color: var(--main-color);
}
.offers .content {
  padding-top: 15px;
}
.offers .item {
  text-align: center;
}
.offers .item .content p {
  color: rgb(133, 134, 140);
  font-size: 15px;
  text-align: center;
}
.offers .item .btn {
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
.offers .item .btn:hover {
  background-color: rgb(160, 209, 95);
  color: rgb(255, 255, 255);
  box-shadow: rgba(0, 0, 0, 0.25) 0px 4px 13px 2px;
}
.offers .slick-prev {
  left: -25px;
}
.offers .slick-next {
  right: -25px;
}
.offers .slick-prev,
.offers .slick-next {
  width: 40px;
  height: 40px;
  z-index: 2;
}
.offers .slick-prev::before,
.offers .slick-next::before {
  font-family: "slick";
  font-size: 40px;
  line-height: 1;
  opacity: 0.75;
  color: var(--main-color);
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
