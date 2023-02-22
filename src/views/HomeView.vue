<template>
  <div class="home">
    <div class="home-content">
      <div class="getstarted">
         <div class="btn">
            <!--Button is here-->
              <button class="button-31" role="button" @click="openButton()" v-if="opened == false">Button 31</button>
         </div>
         <transition name="fade">
           <div class="parent" :class="{ parent2: opened }" :style="{ gridGap: gap + `px` }">
              <div @mouseleave="zindex = 1" @mouseover="gapBiggerGrid()" v-if="opened == true" :class="{ usingone: opened }" class="cards one" :style="{ zIndex: zindex }"></div>
              <div @mouseleave="zindex2 = 1" @mouseover="gapBiggerGrid2()" v-if="opened == true" :class="{ usingtwo: opened }" class="cards two" :style="{ zIndex: zindex2 }"></div>
              <div @mouseleave="zindex3 = 1" @mouseover="gapBiggerGrid3()" v-if="opened == true" :class="{ usingthree: opened }" class="cards three" :style="{ zIndex: zindex3 }"></div>
              <div @mouseleave="zindex4 = 1" @mouseover="gapBiggerGrid4()" v-if="opened == true" :class="{ usingfour: opened }" class="cards four" :style="{ zIndex: zindex4 }"></div>
              <div @mouseleave="zindex5 = 1" @mouseover="gapBiggerGrid5()" v-if="opened == true" :class="{ usingfive: opened }" class="cards five" :style="{ zIndex: zindex5 }"></div>
              <div @mouseleave="zindex6 = 1" @mouseover="gapBiggerGrid6()" v-if="opened == true" :class="{ usingsix: opened }" class="cards six" :style="{ zIndex: zindex6 }"></div>
           </div>       
         </transition>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'HomeView',
  components: {
  },
  data() {
    return {
      opened: false,
      gap: 13,
      zindex: 1,
      zindex2: 1,
      zindex3: 1,
      zindex4: 1,
      zindex5: 1,
      zindex6: 1,
    }
  },
  methods: {
    openButton() {
      this.opened = true
    },
    gapBiggerGrid() {
      this.zindex = 2
    },
    gapBiggerGrid2() {
      this.zindex2 = 2
    },
    gapBiggerGrid3() {
      this.zindex3 = 2
    },
    gapBiggerGrid4() {
      this.zindex4 = 2
    },
    gapBiggerGrid5() {
      this.zindex5 = 2
    },
    gapBiggerGrid6() {
      this.zindex6 = 2
    },
  },
}
</script>
<style scoped>
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.4s;
}
.fade-enter, .fade-leave-to {
  opacity: 0;
}
.home-content {
  display: flex;
  justify-content: center;
  flex-direction: column;
  margin: 200px 0px;
}
/* CSS */
.btn {
  display: flex;
  justify-content: center;
}
.button-31 {
  background-color: #222;
  border-radius: 4px;
  border-style: none;
  color: #fff;
  cursor: pointer;
  font-family: "Farfetch Basis","Helvetica Neue",Arial,sans-serif;
  font-size: 16px;
  font-weight: 700;
  line-height: 1.5;
  max-width: none;
  min-height: 44px;
  min-width: 10px;
  outline: none;
  overflow: hidden;
  position: relative;
  text-align: center;
  text-transform: none;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
  width: 30vw;
}
.cards {
  position: relative;
  height: 25vw;
  width: 29vw;
  background-color: #222;
  border-radius: 5px;
  transition: 0.4s ease-in-out;
}
.parent {
  display: flex;
  justify-content: center;
  margin: -100px 0px;
}
.usingone {
  transition: 0.4s ease-in-out;text-align: center;
}
.usingtwo {
  transition: 0.4s ease-in-out;text-align: center;
}
.usingthree {
  transition: 0.4s ease-in-out;text-align: center;
}
.usingfour {
  transition: 0.4s ease-in-out;text-align: center;
}
.usingfive {
  transition: 0.4s ease-in-out;text-align: center;
}
.usingsix {
  transition: 0.4s ease-in-out;text-align: center;
}
.parent2 {
  display: grid;
  grid-template-columns: auto auto auto;
  animation-name: usingone;
  animation-duration: 0.4s;
  animation-iteration-count: infinite;
}
.usingone:hover, .usingfive:hover, .usingfour:hover, .usingtwo:hover, .usingthree:hover, .usingsix:hover {
  background-color: #363636;
  transform: scale(1.1);
}
@keyframes unsingone {
  0% {
    display: none;
  }
  100% {
    display: grid;
  }
}
</style>