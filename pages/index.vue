<template>
  <div>
    <div class="lines">
      <div class="line"></div>
      <div class="line" style="left: 75%;"></div>
      <div class="line"></div>
    </div>
    <div :class="[ isMobile() ? 'center' : 'right']">
      <div class="" v-show="isActiveSquare" :class="[isActiveSquare ? 'fade-in' : '', isMobile() && isDisableSquare ? 'fade-out' : '']">
        <img src="/square.png" />
      </div>
    </div>
    <div class="center">
      <div class=" fade-in" v-show="isActiveTriangle" :class="[isMobile() && isActiveTriangle ? 'fade-in' : '', isMobile() && isWelcomeMessage ? 'fade-out' : '']">
        <img src="/triangle.png" />
      </div>
    </div>
    <div :class="[ isMobile() ? 'center' : 'left']">
      <div class="" v-show="isActiveCircle" :class="[isActiveCircle ? 'fade-in' : '', isMobile() && isDisableCircle ? 'fade-out' : '']">
        <img src="/circle.png" />
      </div>
    </div>
    <div class="text-blue-50 " :class="[ isMobile() ? 'center text-3xl' : 'top-center text-5xl', isWelcomeMessage ? 'fade-in' : '']" v-show="isWelcomeMessage">Hoşgeldiniz</div>

  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box !important;
}

html, body {
  height: 100%;
}

body {
  display: table;
  width: 100%;
  height: 100%;
  background-color: #171717;
  color: #000;
  line-height: 1.6;
  position: relative;
  font-family: sans-serif;
  overflow: hidden;
}

.center {
  position: absolute;
  left: 50%;
  top: 50%;
  -webkit-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
}
.left {
  position: absolute;
  left: 12.5%;
  top: 50%;
  -webkit-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
}
.right {
  position: absolute;
  right: 0%;
  top: 50%;
  -webkit-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
}

.lines {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 100%;
  margin: auto;
  width: 90vw;
}

.line {
  position: absolute;
  width: 1px;
  height: 100%;
  top: 0;
  left: 50%;
  background: rgba(255, 255, 255, 0.1);
  overflow: hidden;
}
.line::after {
  content: "";
  display: block;
  position: absolute;
  height: 15vh;
  width: 100%;
  top: -50%;
  left: 0;
  background: linear-gradient(to bottom, rgba(255, 255, 255, 0) 0%, #ffffff 75%, #ffffff 100%);
  -webkit-animation: drop 7s 0s infinite;
  animation: drop 7s 0s infinite;
  -webkit-animation-fill-mode: forwards;
  animation-fill-mode: forwards;
  -webkit-animation-timing-function: cubic-bezier(0.4, 0.26, 0, 0.97);
  animation-timing-function: cubic-bezier(0.4, 0.26, 0, 0.97);
}
.line:nth-child(1) {
  margin-left: -25%;
}
.line:nth-child(1)::after {
  -webkit-animation-delay: 2s;
  animation-delay: 2s;
}
.line:nth-child(3) {
  margin-left: 75%;
}
.line:nth-child(3)::after {
  -webkit-animation-delay: 2.5s;
  animation-delay: 2.5s;
}

@-webkit-keyframes drop {
  0% {
    top: -50%;
  }
  100% {
    top: 110%;
  }
}

@keyframes drop {
  0% {
    top: -50%;
  }
  100% {
    top: 110%;
  }
}

.square {
  height: 250px;
  width: 250px;
  background-color: #555;
}
.circle {
  height: 250px;
  width: 250px;
  background-color: #555;
  border-radius: 50%;
  margin: auto;
}
.triangle-up {
  width: 0;
  height: 0;
  border-left: 150px solid transparent;
  border-right: 150px solid transparent;
  border-bottom: 250px solid #555;
}

.fade-in {
  animation: fadeIn ease 5s;
  -webkit-animation: fadeIn ease 5s;
  -moz-animation: fadeIn ease 5s;
  -o-animation: fadeIn ease 5s;
  -ms-animation: fadeIn ease 5s;
}
.fade-in-10 {
  animation: fadeIn ease 30s;
  -webkit-animation: fadeIn ease 30s;
  -moz-animation: fadeIn ease 30s;
  -o-animation: fadeIn ease 30s;
  -ms-animation: fadeIn ease 30s;
}
@keyframes fadeIn {
  0% {
    opacity:0;
  }
  100% {
    opacity:1;
  }
}

@-moz-keyframes fadeIn {
  0% {
    opacity:0;
  }
  100% {
    opacity:1;
  }
}

@-webkit-keyframes fadeIn {
  0% {
    opacity:0;
  }
  100% {
    opacity:1;
  }
}

@-o-keyframes fadeIn {
  0% {
    opacity:0;
  }
  100% {
    opacity:1;
  }
}

@-ms-keyframes fadeIn {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

.fade-out {
  animation: fadeOut ease 5s;
  -webkit-animation: fadeOut ease 5s;
  -moz-animation: fadeOut ease 5s;
  -o-animation: fadeOut ease 5s;
  -ms-animation: fadeOut ease 5s;
}
@keyframes fadeOut {
  0% {
    opacity:1;
  }
  100% {
    opacity:0;
    display: none;
  }
}

@-moz-keyframes fadeOut {
  0% {
    opacity:1;
  }
  100% {
    opacity:0;
    display: none;
  }
}

@-webkit-keyframes fadeOut {
  0% {
    opacity:1;
  }
  100% {
    opacity:0;
    display: none;
  }
}

@-o-keyframes fadeOut {
  0% {
    opacity:1;
  }
  100% {
    opacity:0;
    display: none;
  }
}

@-ms-keyframes fadeOut {
  0% {
    opacity: 1;
  }
  100% {
    opacity: 0;
    display: none;
  }
}
.d-none {
  display: none !important;
}
.top-center {
  margin: auto;
  text-align: center;
  padding-top: 14rem;
}
</style>

<script>
export default {
  data() {
    return {
      isActiveCircle: false,
      isActiveSquare: false,
      isActiveTriangle: true,
      isDisableCircle: false,
      isDisableSquare: false,
      isDisableTriangle: false,
      circleVisible: true,
      squareVisible: true,
      triangleVisible: true,
      isWelcomeMessage: false
    }
  },
  methods:{
    callFunction: function () {
      var v = this;
      if(v.isMobile()) {
        v.isActiveTriangle = false;
        v.isActiveSquare = false
        setTimeout(function(){
          v.isActiveSquare = true;
        }, 5000);
        setTimeout(function() {
          v.isWelcomeMessage = true;
          v.isActiveTriangle = false;
        }, 16000)
        setTimeout(function() {
          window.location.href = "https://www.instagram.com/tv/CW1DaqDDPo1/";
        }, 19000)
      } else {
        setTimeout(function(){
          v.isActiveSquare = true;
        }, 2000);
        setTimeout(function() {
          v.isWelcomeMessage = true;
        }, 4000)
        setTimeout(function() {
          window.location.href = "https://www.instagram.com/tv/CW1DaqDDPo1/";
        }, 8000)
      }
      setTimeout(function(){
        v.isActiveCircle = true;
      }, 1000);
      if(this.isMobile()) {
        setTimeout(function(){
          v.isDisableCircle = true;
        }, 5000);
        setTimeout(function(){
          v.isDisableSquare = true;
        }, 10000);
        setTimeout(function(){
          v.isActiveTriangle = true;
          v.isDisableTriangle = true;
        }, 11000);
      }

    },
    isMobile() {
      if(/Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent)) {
        return true
      } else {
        return false
      }
    },
    hideAll: function () {
      var v = this;
      setTimeout(function(){
        v.isActiveCircle = false;
      }, 10000);
      setTimeout(function(){
        v.isActiveSquare = false;
      }, 15000);
    }
  },
  mounted: function() {
    this.callFunction()
    if(this.isMobile()) {
      this.hideAll()
    }
  },
}
</script>

