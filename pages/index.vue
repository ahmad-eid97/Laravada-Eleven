<template>
  <div class="home">
    <app-home-slider :slides="slides"></app-home-slider>
    <app-home-welcome :whoWeAre="whoWeAre"></app-home-welcome>
    <app-home-services :services="services"></app-home-services>
    <app-home-offers :products="products"></app-home-offers>
    <!-- <app-home-facts></app-home-facts> -->
    <app-home-news :blogs="blogs"></app-home-news>
    <app-home-activities :activities="activities" />
    <app-home-steps :steps="steps" />
    <app-home-banner></app-home-banner>
    <app-home-testimonials :testimonials="testimonials"></app-home-testimonials>
  </div>
</template>

<script>
import AppHomeBanner from "../components/home/AppHomeBanner.vue";
import AppHomeFacts from "../components/home/AppHomeFacts.vue";
import AppHomeNews from "../components/home/AppHomeNews.vue";
import AppHomeOffers from "../components/home/AppHomeOffers.vue";
import AppHomeServices from "../components/home/AppHomeServices.vue";
import AppHomeSlider from "../components/home/AppHomeSlider.vue";
import AppHomeTestimonials from "../components/home/AppHomeTestimonials.vue";
import AppHomeWelcome from "../components/home/AppHomeWelcome.vue";
import AppHomeActivities from "../components/home/AppHomeActivities.vue";
import AppHomeSteps from "../components/home/AppHomeSteps.vue";

export default {
  name: "Home",
  async asyncData({ $axios, app }) {
    const slides = await $axios.get("/sliders", {
      headers: {
        "Accept-Language": app.i18n.locale,
      },
    });

    const whoWeAre = await $axios.get("/sections/who_we_are", {
      headers: {
        "Accept-Language": app.i18n.locale,
      },
    });

    const services = await $axios.get("/services");

    const testimonials = await $axios.get("/testimonials");

    const products = await $axios.get("/products");

    const blogs = await $axios.get("/blogs?latest=1");

    const activities = await $axios.get("/sections/activities", {
      headers: {
        "Accept-Language": app.i18n.locale,
      },
    });

    const steps = await $axios.get("/sections/steps", {
      headers: {
        "Accept-Language": app.i18n.locale,
      },
    });

    return {
      slides: slides.data.data.sliders,
      whoWeAre: whoWeAre.data.data,
      services: services.data.data.services,
      testimonials: testimonials.data.data.testimonials,
      products: products.data.data.products,
      blogs: blogs.data.data.blogs,
      activities: activities.data.data,
      steps: steps.data.data,
    };
  },
  components: {
    AppHomeSlider,
    AppHomeWelcome,
    AppHomeServices,
    AppHomeOffers,
    AppHomeFacts,
    AppHomeNews,
    AppHomeBanner,
    AppHomeTestimonials,
    AppHomeActivities,
    AppHomeSteps,
  },
};
</script>
