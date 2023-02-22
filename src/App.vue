<template>
  <div class="wrapper">
    <nav>
      <font-awesome-icon :icon="faBars" />
      <router-link to="/" class="home" :class="{hover: hovering}" @mouseleave="notHoveringnow()" @mouseenter="hoveringFunction()">Home</router-link> 
      <router-link to="/about" class="about" :class="{hover: hovering2}" @mouseleave="notHoveringnow2()" @mouseenter="hoveringFunction2()"> About</router-link>
    </nav>
  </div>
  <router-view/>
</template>
<script>
import "font-awesome/css/font-awesome.min.css"
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
import { faBars } from '@fortawesome/free-solid-svg-icons'

export default {
  data() {
    return {
      hovering: false,
      hovering2: false,
    }
  },
  methods: {
    hoveringFunction() {
      this.hovering = true
    },
    notHoveringnow() {
      this.hovering = false
    },
    hoveringFunction2() {
      this.hovering2 = true
    },
    notHoveringnow2() {
      this.hovering2 = false
    }
  },
  components: {
    FontAwesomeIcon
  },
  icons: {
    faBars
  },
  computed: {
    faBars: faBars
  }
}
</script>
<style>
@import '@fortawesome/fontawesome-svg-core/styles.css';
font-awesome-icon {
  font-size: 50px;
  color: black;
}
.hover {
  font-size: calc(16px + 5px);
  color: black;
  box-shadow: rgb(36, 36, 36);
}
a {
  transition: 0.2s ease-in-out font-size;
  color: rgb(36, 36, 36);
  text-decoration: none;
  font-weight: bolder;
  font-family: Arial, Helvetica, sans-serif;
  display: flex;
  justify-content: center;
  flex-direction: column;
}
nav {
  display: grid;
  height: 45px;
  background: rgb(106, 106, 106);
  grid-template-columns: 1fr 1fr 1fr;
  grid-template-rows: 45px;
  text-align: center;
  box-shadow: rgba(0, 0, 0, 0.19) 0px 10px 20px, rgba(0, 0, 0, 0.23) 0px 6px 6px;
}
</style>
