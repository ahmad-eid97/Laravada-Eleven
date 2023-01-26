<template>
  <section class="welcome">
    <div class="row m-0">
      <h4>
        {{ whoWeAre.find((one) => one.key === "who_we_are_title").value }}
      </h4>
      <h2>
        {{ whoWeAre.find((one) => one.key === "who_we_are_sub_title").value }}
      </h2>
    </div>
    <div class="row align-items-center m-0">
      <div class="col-lg-6">
        <p>
          {{
            whoWeAre.find((one) => one.key === "who_we_are_description").value
          }}
        </p>
        <div>
          <a
            :href="whoWeAre.find((one) => one.key === 'who_we_are_link').value"
            class="btn"
          >
            Visit dispensary
            <i class="fa-solid fa-shop"></i>
          </a>
        </div>
      </div>
      <div class="col-lg-6">
        <img
          class="img-fluid"
          :src="whoWeAre.find((one) => one.key === 'who_we_are_image').value"
          alt=""
        />
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "AppHomeWelcome",
  props: ["whoWeAre"],
  mounted() {
    document
      .querySelector(".welcome")
      .style.setProperty(
        "--whoWeAre-bg",
        this.whoWeAre.find(
          (one) => one.key === "who_we_are_background_active_section"
        ).value === "color"
          ? this.whoWeAre.find(
              (one) => one.key === "who_we_are_background_color_section"
            ).value
          : `url(${
              this.whoWeAre.find(
                (one) => one.key === "who_we_are_background_image_section"
              ).value
            })`
      );

    document
      .querySelector(".welcome")
      .style.setProperty(
        "--whoWeAre-fontSize",
        `${
          this.whoWeAre.find(
            (one) => one.key === "who_we_are_font_size_section"
          ).value
        }px`
      );

    if (
      this.whoWeAre.find(
        (one) => one.key === "who_we_are_border_position_section"
      ) &&
      this.whoWeAre.find(
        (one) => one.key === "who_we_are_border_position_section"
      ).value === "both"
    ) {
      document
        .querySelector(".welcome")
        .style.setProperty(
          "--whoWeAre-border-top",
          `${
            this.whoWeAre.find(
              (one) => one.key === "who_we_are_border_size_section"
            ).value
          }px ${
            this.whoWeAre.find(
              (one) => one.key === "who_we_are_border_type_section"
            ).value
          } ${
            this.whoWeAre.find(
              (one) => one.key === "who_we_are_border_color_section"
            ).value
          }`
        );

      document
        .querySelector(".welcome")
        .style.setProperty(
          "--whoWeAre-border-bottom",
          `${
            this.whoWeAre.find(
              (one) => one.key === "who_we_are_border_size_section"
            ).value
          }px ${
            this.whoWeAre.find(
              (one) => one.key === "who_we_are_border_type_section"
            ).value
          } ${
            this.whoWeAre.find(
              (one) => one.key === "who_we_are_border_color_section"
            ).value
          }`
        );
    } else if (
      this.whoWeAre.find(
        (one) => one.key === "who_we_are_border_position_section"
      ) &&
      this.whoWeAre.find(
        (one) => one.key === "who_we_are_border_position_section"
      ).value === "top"
    ) {
      document
        .querySelector(".welcome")
        .style.setProperty(
          "--whoWeAre-border-top",
          `${
            this.whoWeAre.find(
              (one) => one.key === "who_we_are_border_size_section"
            ).value
          }px ${
            this.whoWeAre.find(
              (one) => one.key === "who_we_are_border_type_section"
            ).value
          } ${
            this.whoWeAre.find(
              (one) => one.key === "who_we_are_border_color_section"
            ).value
          }`
        );
    } else if (
      this.whoWeAre.find(
        (one) => one.key === "who_we_are_border_position_section"
      ) &&
      this.whoWeAre.find(
        (one) => one.key === "who_we_are_border_position_section"
      ).value === "bottom"
    ) {
      document
        .querySelector(".welcome")
        .style.setProperty(
          "--whoWeAre-border-bottom",
          `${
            this.whoWeAre.find(
              (one) => one.key === "who_we_are_border_size_section"
            ).value
          }px ${
            this.whoWeAre.find(
              (one) => one.key === "who_we_are_border_type_section"
            ).value
          } ${
            this.whoWeAre.find(
              (one) => one.key === "who_we_are_border_color_section"
            ).value
          }`
        );
    }
  },
};
</script>

<style lang="scss">
.welcome {
  padding: 70px 50px;
  --whoWeAre-bg: #fff;
  --whoWeAre-fontSize: 20px;
  --whoWeAre-border-top: 0px solid #fff;
  --whoWeAre-border-bottom: 0px solid #fff;

  background: var(--whoWeAre-bg);
  border-top: var(--whoWeAre-border-top);
  border-bottom: var(--whoWeAre-border-bottom);
  background-repeat: no-repeat;
  background-size: cover;
  padding: 50px 0 50px;

  h1 {
    font-size: var(--whoWeAre-fontSize);
    text-align: center;
  }
}
@include sm {
  .welcome {
    padding: 50px 10px;
  }
}
.welcome h4 {
  color: rgb(117, 179, 37);
  font-size: 18px;
  font-weight: 700;
  line-height: 28px;
  margin-bottom: 10px;
  text-align: center;
}
.welcome h2 {
  color: rgb(51, 51, 51);
  font-size: 34px;
  font-weight: 700;
  line-height: 44px;
  text-align: center;
  padding: 0 25px 70px;
}
@include sm {
  .welcome h2 {
    font-size: 25px;
    line-height: 35px;
  }
}
.welcome h3 {
  color: rgb(51, 51, 51);
  font-size: 20px;
  font-weight: 700;
  line-height: 26px;
  margin-bottom: 15px;
  text-align: left;
}
.welcome p {
  color: rgb(133, 134, 140);
  font-size: 15px;
  font-weight: 400;
  line-height: 25.5px;
  margin-bottom: 20px;
  text-align: left;
}
.welcome .btn {
  background-color: rgb(117, 179, 37);
  border-radius: 3px;
  border: none;
  color: rgb(255, 255, 255);
  cursor: pointer;
  font-size: 15px;
  font-weight: 700;
  height: 50px;
  line-height: 20px;
  padding-bottom: 15px;
  padding-left: 35px;
  padding-right: 35px;
  padding-top: 15px;
  margin-bottom: 10px;
  margin-left: 0px;
  margin-right: 10px;
  margin-top: 0px;
  min-width: 200px;
}
.welcome .btn:hover {
  background-color: rgb(160, 209, 95);
  color: rgb(255, 255, 255);
}
</style>
