<template>
  <div class="home">
    <app-home-slider :slides="slides"></app-home-slider>
    <app-home-partners :partners="partners" />
    <div v-if="$store.state.sectionsStatus.who_we_are">
      <app-home-welcome :whoWeAre="whoWeAre.data"></app-home-welcome>
    </div>
    <app-home-services :services="services"></app-home-services>
    <app-home-offers :products="products"></app-home-offers>
    <!-- <app-home-facts></app-home-facts> -->
    <app-home-news :blogs="blogs"></app-home-news>
    <div v-if="$store.state.sectionsStatus.activities">
      <app-home-activities :activities="activities.data" />
    </div>
    <div v-if="$store.state.sectionsStatus.steps">
      <app-home-steps :steps="steps.data" />
    </div>
    <app-home-banner></app-home-banner>
    <app-home-testimonials :testimonials="testimonials"></app-home-testimonials>
    <SocialChat :attendants="attendants">
      <p slot="header">Click one of our representatives below to chat.</p>
      <template v-slot:button="{ open }">
        <span v-show="!open">Contact us</span>
        <span v-show="open">Close</span>
      </template>
      <small slot="footer">Opening hours: 8am to 10pm</small>
    </SocialChat>
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
import AppHomePartners from "../components/home/AppHomePartners.vue";

export default {
  name: "Home",
  data() {
    return {
      attendants: [
        {
          app: "whatsapp",
          label: "Support",

          name: this.$store.state.websiteSettings.find(
            (one) => one.key === "chat_widget_whatsapp_label"
          )
            ? this.$store.state.websiteSettings.find(
                (one) => one.key === "chat_widget_whatsapp_label"
              ).plain_value
            : "Laravada",

          number: this.$store.state.websiteSettings.find(
            (one) => one.key === "chat_widget_whatsapp_number"
          )
            ? this.$store.state.websiteSettings.find(
                (one) => one.key === "chat_widget_whatsapp_number"
              ).plain_value
            : "11111111111",

          avatar: {
            src: "https://avatars0.githubusercontent.com/u/8084606?s=460&u=20b6499a416cf7129a18e5c168cf387e159edb1a&v=4",
            alt: "Laravada customer support",
          },
        },
        {
          app: "messenger",
          label: "Technical support",

          name: this.$store.state.websiteSettings.find(
            (one) => one.key === "chat_widget_messenger_label"
          )
            ? this.$store.state.websiteSettings.find(
                (one) => one.key === "chat_widget_messenger_label"
              ).plain_value
            : "Laravada Facebook",

          id: this.$store.state.websiteSettings.find(
            (one) => one.key === "chat_widget_messenger_id"
          )
            ? this.$store.state.websiteSettings.find(
                (one) => one.key === "chat_widget_messenger_id"
              ).plain_value
            : "111111111111",

          avatar: {
            src: "https://avatars0.githubusercontent.com/u/8084606?s=460&u=20b6499a416cf7129a18e5c168cf387e159edb1a&v=4",
            alt: "Laravada customer support",
          },
        },
      ],
    };
  },
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

    const partners = await $axios.get("/partners");

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
      partners: partners.data.data.partners,
      whoWeAre: whoWeAre.data,
      services: services.data.data.services,
      testimonials: testimonials.data.data.testimonials,
      products: products.data.data.products,
      blogs: blogs.data.data.blogs,
      activities: activities.data,
      steps: steps.data,
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
    AppHomePartners,
  },
};
</script>

<style>
.home {
  --vsc-bg-header: var(--main-color);
  --vsc-bg-footer: var(--main-color);
  --vsc-text-color-header: #fff;
  --vsc-text-color-footer: #fff;
  --vsc-bg-button: var(--main-color);
  --vsc-text-color-button: #fff;
  --vsc-outline-color: var(--main-color);
  --vsc-border-color-bottom-header: #fff;
  --vsc-border-color-top-footer: #fff;
}
</style>
