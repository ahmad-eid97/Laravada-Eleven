<template>
  <footer>
    <div class="widgets">
      <div class="row m-0">
        <div class="col-sm-6 col-md-4">
          <h5>Get in touch!</h5>
          <div>
            <h6>Mail</h6>
            <p>info@railcoder.com</p>
          </div>
          <div>
            <h6>Call us</h6>
            <p>011 322 44 56</p>
          </div>
          <div>
            <h6>Address</h6>
            <p>8500 Beverly Boulevard Los Angeles, CA 90048</p>
          </div>
          <div>
            <h6>Business hours</h6>
            <p>We are open 7 days a week from 7am to 9pm</p>
          </div>
          <div>
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
          <h5>News</h5>
          <div style="margin-bottom: 15px">
            <div class="row m-0">
              <div class="col-auto p-0">
                <img
                  src="https://the7.io/weed/wp-content/uploads/sites/51/2019/01/weed015-60x60.jpg"
                  width="60"
                  height="60"
                  alt=""
                />
              </div>
              <div class="col">
                <h6>Nulla iaculis efficitu from weed</h6>
                <p>29th January 2019</p>
              </div>
            </div>
          </div>
          <div style="margin-bottom: 15px">
            <div class="row m-0">
              <div class="col-auto p-0">
                <img
                  src="https://the7.io/weed/wp-content/uploads/sites/51/2019/01/weed015-60x60.jpg"
                  width="60"
                  height="60"
                  alt=""
                />
              </div>
              <div class="col">
                <h6>Nulla iaculis efficitu from weed</h6>
                <p>29th January 2019</p>
              </div>
            </div>
          </div>
          <div style="margin-bottom: 15px">
            <div class="row m-0">
              <div class="col-auto p-0">
                <img
                  src="https://the7.io/weed/wp-content/uploads/sites/51/2019/01/weed015-60x60.jpg"
                  width="60"
                  height="60"
                  alt=""
                />
              </div>
              <div class="col">
                <h6>Nulla iaculis efficitu from weed</h6>
                <p>29th January 2019</p>
              </div>
            </div>
          </div>
          <div style="margin-bottom: 15px">
            <div class="row m-0">
              <div class="col-auto p-0">
                <img
                  src="https://the7.io/weed/wp-content/uploads/sites/51/2019/01/weed015-60x60.jpg"
                  width="60"
                  height="60"
                  alt=""
                />
              </div>
              <div class="col">
                <h6>Nulla iaculis efficitu from weed</h6>
                <p>29th January 2019</p>
              </div>
            </div>
          </div>
        </div>
        <div class="col-sm-6 col-md-4">
          <h5>Our products</h5>
          <div style="margin-bottom: 15px">
            <div class="row m-0">
              <div class="col-auto p-0">
                <img
                  src="https://the7.io/weed/wp-content/uploads/sites/51/2019/01/s013-300x386.jpg"
                  width="60"
                  height="77.2"
                  alt=""
                />
              </div>
              <div class="col">
                <h6>Cannabis Oil Light</h6>
                <p>$19.00</p>
              </div>
            </div>
          </div>
          <div style="margin-bottom: 15px">
            <div class="row m-0">
              <div class="col-auto p-0">
                <img
                  src="https://the7.io/weed/wp-content/uploads/sites/51/2019/01/s013-300x386.jpg"
                  width="60"
                  height="77.2"
                  alt=""
                />
              </div>
              <div class="col">
                <h6>Cannabis Oil Light</h6>
                <p>$19.00</p>
              </div>
            </div>
          </div>
          <div style="margin-bottom: 15px">
            <div class="row m-0">
              <div class="col-auto p-0">
                <img
                  src="https://the7.io/weed/wp-content/uploads/sites/51/2019/01/s013-300x386.jpg"
                  width="60"
                  height="77.2"
                  alt=""
                />
              </div>
              <div class="col">
                <h6>Cannabis Oil Light</h6>
                <p>$19.00</p>
              </div>
            </div>
          </div>
          <div style="margin-bottom: 15px">
            <div class="row m-0">
              <div class="col-auto p-0">
                <img
                  src="https://the7.io/weed/wp-content/uploads/sites/51/2019/01/s013-300x386.jpg"
                  width="60"
                  height="77.2"
                  alt=""
                />
              </div>
              <div class="col">
                <h6>Cannabis Oil Light</h6>
                <p>$19.00</p>
              </div>
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
          1 (234) 567-891
        </span>
      </p>
    </div>
  </footer>
</template>

<script>
export default {
  name: "AppFooter",
  components: {},
  data() {
    return {};
  },
  beforeMount() {},
  methods: {},
};
</script>
<style>
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
footer .widgets a {
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
</style>
