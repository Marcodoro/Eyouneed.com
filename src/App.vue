<template>
  <nav>
    <router-link to="/" class="home" :class="{}" :style="{home}">Home</router-link> |
    <router-link to="/about" class="about" :class="{ hover: hovering }" @mouseover="hover()">About</router-link>
  </nav>
  <router-view/>
</template>
<script>
export default {
  data() {
    return {
      hovering: true,
      home: {
        color: `yellow`,
      }
    }
  },
  computed: {

  },
  methods: {
    hover() {
    }
  },
}
</script>
<style>
.about {
  color: #b40202;
}
</style>
