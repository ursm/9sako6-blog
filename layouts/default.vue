<template>
  <div id="root">
    <div id="container-outer">
      <Header />
      <div class="color-mode-picker-container">
        <ColorModePicker />
      </div>
      <div id="content">
        <nuxt id="page-main" keep-alive />
        <aside id="side-menu">
          <Profile />
          <Tags />
        </aside>
      </div>
    </div>
    <div class="color-mode-picker-container">
      <ColorModePicker />
    </div>
    <Footer />
  </div>
</template>
<script>
import ColorModePicker from '~/components/ColorModePicker';
import Header from '~/components/Header.vue';
import Profile from '~/components/Profile.vue';
import Tags from '~/components/Tags.vue';
import Footer from '~/components/Footer.vue';

export default {
  components: {
    Header,
    Profile,
    Tags,
    Footer,
    ColorModePicker
  }
};
</script>

<style lang="scss" scoped>
#root {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.color-mode-picker-container {
  text-align: center;
  padding: 1rem;
}

html {
  @apply font-medium;
  font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    "Helvetica Neue", Arial, "Noto Sans", sans-serif, "Apple Color Emoji",
    "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
  font-size: 14px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
  color: #3f3f3f;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}
.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}
.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3f3f3f;
  color: #3f3f3f;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}
.button--grey:hover {
  color: #fff;
  background-color: #3f3f3f;
}
@media screen and (max-width: 767px) {
  #container-outer {
    width: 100%;
    margin: auto;
  }
  #page-main {
    width: 100%;
  }
  #side-menu {
    width: 100%;
  }
  #content {
    margin: 0 10px;
  }
}
@media screen and (min-width: 768px) {
  #container-outer {
    width: 90%;
  }
  #page-main {
    width: 100%;
  }
  #side-menu {
    width: 100%;
  }
  #content {
    margin: 0px 55px;
  }
}
@media screen and (min-width: 1200px) {
  #container-outer {
    width: 1140px;
  }
  #content {
    margin: 0px 55px;
  }
}
#container-outer {
  margin: auto;
  margin-bottom: 100px;
}
#page-main {
  float: left;
  margin-bottom: 100px;
}

a {
  word-break: break-all;

  &:hover {
    text-decoration: underline;
  }
}
</style>
