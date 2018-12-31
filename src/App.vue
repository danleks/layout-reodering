<template>
  <div id="app">
    <main class="mainWrapper">
      <Menu @toggle-menu="toggleMenu" :menuOn="menuOn"/>
      <Heading />
      <Claim />
      <Form />
      <Img />
    </main>
    <Footer />
  </div>
</template>

<script>
import Claim from './components/Claim.vue';
import Footer from './components/Footer.vue';
import Form from './components/Form.vue';
import Heading from './components/Heading.vue';
import Img from './components/Image.vue';
import Menu from './components/Menu.vue';

export default {
  name: 'app',
  components: {
    Claim,
    Footer,
    Form,
    Heading,
    Img,
    Menu,
  },

  data() {
    return {
      menuOn: false,
    }
  },

  methods: {
    toggleMenu() {
      this.menuOn = !this.menuOn;
    }
  }
};
</script>

<style lang="scss">

html {
  box-sizing: border-box;
  height: 100%;
}
*, *:before, *:after {
  box-sizing: inherit;
  padding: 0;
  margin: 0;
  -webkit-tap-highlight-color: transparent;
}

#app {
  display: flex;
  flex-direction: column;
  height: 100vh;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

   @media(min-width: 1024px) {
    width: 1024px;
    margin: auto;
  }
}

.mainWrapper {
  flex: 1 0 auto;

  display: flex;
  flex-direction: column;

  & > * {
    order: 999;
  }
}
</style>
