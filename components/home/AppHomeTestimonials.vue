<template>
    <section class="testimonials">
        <div class="row m-0">
            <h2>
                What our customers say
            </h2>
        </div>
        <VueSlickCarousel :slidesToShow = "1" :slidesToScroll = "1" :arrows="true" :dots="false">
            <div v-for="item in testimonials" :key="item.id">
                <div class="item">
                    <div class="row m-0 insider">
                        <div class="col-auto">
                            <img :src="item.image" :alt="item.title">
                        </div>
                        <div class="col">
                            <p>
                                {{item.description}}
                            </p>
                            <h3>
                                {{item.username}}
                            </h3>
                            <h4>
                                {{item.job}}
                            </h4>
                        </div>
                    </div>
                </div>
            </div>
        </VueSlickCarousel>
    </section>
</template>

<script>
import VueSlickCarousel from 'vue-slick-carousel'
import 'vue-slick-carousel/dist/vue-slick-carousel.css'
import 'vue-slick-carousel/dist/vue-slick-carousel-theme.css'
export default {
    components: { VueSlickCarousel },
    props: ["testimonials"],
    name: 'AppHomeTestimonials'
}
</script>

<style lang="scss">
    .testimonials {
        padding: 80px 50px 70px;
        background-color: rgb(117, 179, 37);
    }
    .testimonials h2 {
        color: rgb(255, 255, 255);
        font-size: 34px;
        font-weight: 700;
        line-height: 44px;
        text-align: center;
        margin-bottom: 70px;
    }
    .testimonials .item {
        max-width: 770px;
        border: 4px dashed #9fca67;
        padding: 40px;
        margin: 0 auto;
    }
    .testimonials .item .insider {
        align-items: center;
    }
    @include xs {
        .testimonials .item {
            padding: 10px;
        }
    }
    @include sm {
        .testimonials .item .row {
            display: block;
        }
    }
    .testimonials .item img {
        width: 150px;
        height: 150px;
        border-radius: 50%;
    }
    .testimonials .item p {
        color: rgb(255, 255, 255);
        font-size: 17px;
        font-style: italic;
        line-height: 30px;
        margin-bottom: 10px;
    }
    .testimonials .item h3 {
        color: rgb(255, 255, 255);
        font-size: 24px;
        font-weight: 700;
        line-height: 34px;
    }
    .testimonials .item h4 {
        color: rgb(255, 255, 255);
        font-size: 14px;
        font-weight: 700;
        line-height: 21px;
    }
    .testimonials .slick-prev {
        left: -25px;
    }
    .testimonials .slick-next {
        right: -25px;
    }
    .testimonials .slick-prev, .testimonials .slick-next {
        width: 40px;
        height: 40px;
        z-index: 2;
    }
    .testimonials .slick-prev::before, .testimonials .slick-next::before {
        font-family: 'slick';
        font-size: 40px;
        line-height: 1;
        opacity: 0.75;
        color: #fff;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
    }
</style>