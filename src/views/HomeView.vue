<template>
  <div class="home">
    <div class="home-content">
      <div class="getstarted">
         <div class="btn">
            <!--Button is here-->
              <button class="button-31" role="button" @click="openButton()" v-if="opened == false">Learn to Programm</button>
         </div>
         <transition name="fade">
           <div class="parent" :class="{ parent2: opened }" :style="{ gridGap: gap + `px` }">
              <div @click="check1()" @mouseleave="zindex = 1" @mouseover="gapBiggerGrid()" v-if="opened == true" :class="{ usingone: opened }" class="cards one" :style="{ zIndex: zindex }">
                Learn Html,css and js
              </div>
              <div @click="check2()" @mouseleave="zindex2 = 1" @mouseover="gapBiggerGrid2()" v-if="opened == true" :class="{ usingtwo: opened }" class="cards two" :style="{ zIndex: zindex2 }">
                Learn C#
              </div>
              <div @click="check3()" @mouseleave="zindex3 = 1" @mouseover="gapBiggerGrid3()" v-if="opened == true" :class="{ usingthree: opened }" class="cards three" :style="{ zIndex: zindex3 }">
                Learn Vuejs
              </div>
              <div @click="check4()" @mouseleave="zindex4 = 1" @mouseover="gapBiggerGrid4()" v-if="opened == true" :class="{ usingfour: opened }" class="cards four" :style="{ zIndex: zindex4 }">
                Learn Python
              </div>
              <div @click="check5()" @mouseleave="zindex5 = 1" @mouseover="gapBiggerGrid5()" v-if="opened == true" :class="{ usingfive: opened }" class="cards five" :style="{ zIndex: zindex5 }">
                Learn how to deploy your website
              </div>
              <div @click="check6()" @mouseleave="zindex6 = 1" @mouseover="gapBiggerGrid6()" v-if="opened == true" :class="{ usingsix: opened }" class="cards six" :style="{ zIndex: zindex6 }">
                Learn Firebase
              </div>
           </div>    
          </transition>
           <div class="next">
            <button @click="choosen()" class="next-btn" v-if="option != null">Confirm <br> <span class="op">{{ option }}</span></button>
           </div>   
      </div>
    </div>
    <div class="html">

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
      opened: true,
      gap: 13,
      zindex: 1,
      zindex2: 1,
      zindex3: 1,
      zindex4: 1,
      zindex5: 1,
      zindex6: 1,
      option: null,
      num: 1,
    }
  },
  methods: {
    check1() {
      this.option = "Html,css and js"
    },
    check2() {
      this.option = "C#"
    },
    check3() {
      this.option = "Vue.js"
    },
    check4() {
      this.option = "Python"
    },
    check5() {
      this.option = "Deployment"
    },
    check6() {
      this.option = "Firebase"
    },
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
    choosen() {

    }
  },
}
</script>
<style scoped>
a {
  text-decoration: none;
  color: rgb(0, 0, 0);
}
.next > .next-btn > span {
  font-weight: bolder;
}
.next {
  height: 600px;
  display: flex;
  justify-content: center;
}
.next-btn {
  width: 18vw;
  height: 7vw;
  background-color: #5cd0d8;
  border: none;
  border-radius: 3px;
  transition: ease-in-out 0.3s;
  min-height: 40px;
  min-width: 100px;
  font-family: "Farfetch Basis","Helvetica Neue",Arial,sans-serif;
  margin: 150px 0px;
  font-size: 1.42vw;
  cursor: pointer;
  box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
}
.next-btn:hover {
  background-color: #29cdd9;
  box-shadow: rgba(42, 184, 184, 0.35) 0px 5px 15px;
}
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
  margin: 145px 0px;
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
  max-height: 300px;
  max-width: 300px;
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  color: white;
  font-weight: bolder;
  box-shadow: rgba(0, 0, 0, 0.25) 0px 14px 28px, rgba(0, 0, 0, 0.22) 0px 10px 10px;
  font-size: 2vw;
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
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
  font-size: calc(2vw + 6px);
  box-shadow: rgba(0, 0, 0, 0.25) 0px 54px 55px, rgba(0, 0, 0, 0.12) 0px -12px 30px, rgba(0, 0, 0, 0.12) 0px 4px 6px, rgba(0, 0, 0, 0.17) 0px 12px 13px, rgba(0, 0, 0, 0.09) 0px -3px 5px;
}
@keyframes unsingone {
  0% {
    display: none;
  }
  100% {
    display: grid;
  }
}
@media only screen and (max-width: 1100px) {
  .cards {
    max-width: 200px;
  }
}
</style>