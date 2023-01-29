<template>
  <footer>
    <subscribe />
    <div class="widgets">
      <div class="row m-0">
        <div class="col-sm-6 col-md-4">
          <h5>Get in touch!</h5>
          <div>
            <h6>Mail</h6>
            <p>
              {{
                $store.state.websiteSettings.find((one) => one.key === "email")
                  .plain_value
              }}
            </p>
          </div>
          <div>
            <h6>Call us</h6>
            <p>
              {{
                $store.state.websiteSettings.find(
                  (one) => one.key === "contact_phone"
                ).plain_value
              }}
            </p>
          </div>
          <div>
            <h6>Address</h6>
            <p>
              {{
                $store.state.websiteSettings.find(
                  (one) => one.key === "contact_address"
                ).plain_value
              }}
            </p>
          </div>
          <div class="social">
            <a
              :href="`https://${$store.state.footerData.facebook}`"
              target="_blank"
            >
              <i class="fa-brands fa-facebook-f"></i>
            </a>
            <a
              :href="`https://${$store.state.footerData.twitter}`"
              target="_blank"
            >
              <i class="fa-brands fa-twitter"></i>
            </a>
            <a
              :href="`https://${$store.state.footerData.youtube}`"
              target="_blank"
            >
              <i class="fa-brands fa-youtube"></i>
            </a>
            <a
              :href="`https://${$store.state.footerData.instagram}`"
              target="_blank"
            >
              <i class="fa-brands fa-instagram"></i>
            </a>
          </div>
        </div>
        <div class="col-sm-6 col-md-4">
          <div class="footer-item">
            <div class="footer-title">
              <h6>Useful Links</h6>
            </div>
            <ul class="footer-list">
              <!-- <li><a href="#">About Us</a></li> -->
              <li>
                <nuxt-link :to="localePath('/about')">About Us</nuxt-link>
              </li>
              <li>
                <nuxt-link :to="localePath('/services')">Services</nuxt-link>
              </li>
              <li>
                <nuxt-link :to="localePath('/team')">Team</nuxt-link>
              </li>
              <li>
                <nuxt-link :to="localePath('/testimonials')">Gallery</nuxt-link>
              </li>
              <li>
                <nuxt-link :to="localePath('/blogs')">Blogs</nuxt-link>
              </li>
              <li>
                <nuxt-link :to="localePath('/contact')">Contact</nuxt-link>
              </li>
            </ul>
          </div>
        </div>
        <div class="col-sm-6 col-md-4">
          <div class="footer-item">
            <div class="footer-title">
              <h6>OTHER PAGES</h6>
              <ul class="footer-list">
                <!-- <li><a href="#">About Us</a></li> -->
                <li v-for="page in $store.state.footerPages" :key="page.id">
                  <nuxt-link
                    :to="localePath(generatePagePath(page.id))"
                    v-if="page.status"
                    >{{ page.name }}</nuxt-link
                  >
                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="copyrights">
      <p>
        © Powered By: Rail Coder 2016-2017. All rights reserved.
        <span class="mx-2" style="float: right">
          <i class="fa-solid fa-envelope"></i>
          {{
            $store.state.websiteSettings.find((one) => one.key === "email")
              .plain_value
          }}
        </span>
        <span class="mx-2" style="float: right">
          <i class="fa-solid fa-square-phone"></i>

          {{
            $store.state.websiteSettings.find(
              (one) => one.key === "contact_phone"
            ).plain_value
          }}
        </span>
      </p>
    </div>
  </footer>
</template>

<script>
import Subscribe from "../subscribe/subscribe.vue";
export default {
  name: "AppFooter",
  components: { Subscribe },
  data() {
    return {};
  },
  beforeMount() {},
  methods: {
    generatePagePath(id) {
      switch (id) {
        case 1:
          return "/about";
        case 2:
          return "/contact";
        case 3:
          return "/terms";
        case 4:
          return "/policy";
      }
    },
  },
};
</script>
<style lang="scss">
footer {
  padding: 20px 65px;
  background: #1a1c20
    url(https://the7.io/weed/wp-content/themes/dt-the7/images/backgrounds/patterns/full/binding_dark.gif)
    repeat center top;
}
footer .copyrights {
  border-top: 1px solid #343434;
  padding: 20px 65px;
}
footer .copyrights p {
  color: rgb(255, 255, 255);
  font-size: 13px;
  font-weight: 400;
  line-height: 18.2px;
  text-align: left;
  margin: 0;
}
footer h5 {
  color: rgb(255, 255, 255);
  font-size: 15px;
  line-height: 19.5px;
  margin-bottom: 20px;
}
footer h6 {
  color: rgb(255, 255, 255);
  font-size: 14px;
  line-height: 21px;
  margin-bottom: 5px;
  font-size: 14px;
  line-height: 21px;
  margin-bottom: 5px;
}
footer p {
  color: rgb(133, 134, 140);
  font-size: 14px;
  line-height: 21px;
}
footer .widgets .social {
  margin-bottom: 20px;
}
footer .widgets .social a {
  background-color: rgba(133, 134, 140, 0.15);
  border-radius: 50%;
  color: rgb(133, 134, 140);
  font-size: 14px;
  height: 26px;
  line-height: 26px;
  margin-bottom: 2px;
  margin-left: 2px;
  margin-right: 2px;
  margin-top: 2px;
  position: relative;
  text-align: center;
  width: 26px;
  display: inline-block;
}
.footer-list {
  padding: 0;
  list-style: none;
  li {
    padding: 5px 0;
    a {
      color: #fff;
      font-size: 0.9rem;
    }
  }
}
</style>
