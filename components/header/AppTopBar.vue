<template>
  <div class="topbar">
    <div class="row m-0 justify-content-between">
      <div class="col-auto d-flex">
        <a href="#">
          <i class="fa-solid fa-user-lock"></i>
          My account
        </a>
        <a href="#">
          <i class="fa-solid fa-arrow-right-arrow-left"></i>
          Order tracking
        </a>
      </div>
      <div class="col-auto d-flex">
        <div class="form">
          <input
            type="text"
            value=""
            placeholder="Search..."
            title="Search form"
          />
          <i class="fa-solid fa-magnifying-glass"></i>
        </div>
        <a href="#">
          <i class="fa-solid fa-phone"></i>
          +11111111111111
        </a>
        <a href="#">
          <div class="icon">
            <i class="fa-brands fa-facebook-f"></i>
          </div>
        </a>
        <a href="#">
          <div class="icon">
            <i class="fa-brands fa-twitter"></i>
          </div>
        </a>
        <a href="#">
          <div class="icon">
            <i class="fa-brands fa-dribbble"></i>
          </div>
        </a>
        <lang-switch />
      </div>
    </div>
  </div>
</template>

<script>
import LangSwitch from '../langSwitch/langSwitch.vue';
export default {
  name: "AppTopBar",
  components: {
    LangSwitch
  },
};
</script>

<style lang="scss">
.topbar {
  padding-bottom: 5px;
  padding-left: 50px;
  padding-right: 50px;
  padding-top: 5px;
  background-color: var(--main-color);
}
@include md {
  .topbar {
    display: none;
  }
}
.topbar a {
  align-items: center;
  color: rgb(255, 255, 255);
  font-size: 15px;
  font-weight: 500;
  line-height: 30px;
  text-decoration: none;
  margin-right: 16px;
  display: inline-block;
}
.topbar a i {
  color: rgba(255, 255, 255, 0.5);
  font-size: 16px;
  font-weight: 900;
  line-height: 16px;
  margin-right: 5.35714px;
}
.topbar .form {
  position: relative;
  width: 150px;
  display: inline-block;
  margin: 0 10px;
}
.topbar .form input {
  background-color: rgba(0, 0, 0, 0);
  border: 1px solid rgba(255, 255, 255, 0.3);
  border-radius: 3px;
  color: rgb(255, 255, 255);
  font-size: 12px;
  font-weight: 400;
  height: 28px;
  line-height: 26px;
  margin-left: 0px;
  margin-right: 0px;
  margin-top: 0px;
  max-width: 100%;
  min-height: 26px;
  padding-left: 12px;
  padding-right: 12px;
  width: 150px;
  outline: none;
}
.topbar .form input::placeholder {
  color: #fff;
}
.topbar .form i {
  color: rgb(255, 255, 255);
  font-size: 15px;
  top: 6px;
  line-height: 21px;
  position: absolute;
  right: 12px;
}
.topbar .icon {
  border-radius: 3px;
  box-sizing: border-box;
  color: rgb(255, 255, 255);
  font-size: 15px;
  height: 28px;
  line-height: 28px;
  position: relative;
  text-align: center;
  width: 28px;
  border: 1px solid #9fca67;
}
.topbar .icon i {
  color: #fff;
  margin: 0;
}
.topbar .icon i {
  color: #fff;
  margin: 0;
}
.topbar .icon:hover {
  background-color: #9fca67;
}
</style>
