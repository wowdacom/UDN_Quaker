<template>
    <div class="animation-map" ref="animation-map">
        
        <div class="map-wrapper" ref="map-start">
        <div class="map enterMap" 
            :style="handleMapStyle">
            <h3 class="map-title" ref="title" :class="{ 'map-title-active': map.title.isShow }">4個月至3歲副食品 建議一日攝取量</h3>
            <div class="target1 targets" :src="map.target.src">
              <div class="kernel"></div>
            </div>
            <div class="target2 targets" :src="map.target.src">
              <div class="kernel"></div>
            </div>
            <div class="target3 targets" :src="map.target.src">
              <div class="kernel"></div>
            </div>
            <div class="target4 targets" :src="map.target.src">
              <div class="kernel"></div>
            </div>
            <div class="target5 targets" :src="map.target.src">
              <div class="kernel"></div>
            </div>
        </div>
        </div>
        <div class="map-hints1" ref="hints1">
            <img :src="mapAnimation.hints[0].img" alt="">
        </div>
        <div class="map-hints2" ref="hints2">
            <img :src="mapAnimation.hints[1].img" alt="">
        </div>
        <div class="map-hints3" ref="hints3">
            <img :src="mapAnimation.hints[2].img" alt="">
        </div>
        <div class="map-hints4" ref="hints4">
            <img :src="mapAnimation.hints[3].img" alt="">
        </div>
        <div class="map-hints5" ref="hints5">
            <img :src="mapAnimation.hints[4].img" alt="">
        </div>
        <div class="map-wrapper" ref="map-end">
        <div class="map leaveMap"
            :style="handleMapStyle"
        >
            <h3 class="map-title" ref="title" :class="{ 'map-title-active': map.title.isShow }">4個月至3歲副食品 建議一日攝取量</h3>
            <div class="target1 targets" :class="{ 'isShow': targets.target1.isShow }" :src="map.target.src">
              <div class="kernel"></div>
            </div>
            <div class="target2 targets" :class="{ 'isShow': targets.target2.isShow }" :src="map.target.src">
              <div class="kernel"></div>
            </div>
            <div class="target3 targets" :class="{ 'isShow': targets.target3.isShow }" :src="map.target.src">
              <div class="kernel"></div>
            </div>
            <div class="target4 targets" :class="{ 'isShow': targets.target4.isShow }" :src="map.target.src">
              <div class="kernel"></div>
            </div>
            <div class="target5 targets" :class="{ 'isShow': targets.target5.isShow }" :src="map.target.src">
              <div class="kernel"></div>
            </div>
        </div>
        </div>
    </div>  
</template>

<script>
import _throttle from 'lodash.throttle'

export default {
  name: 'AnimationMap',
  watch: {
    screenWidth (size) {
      this.screenWidth = size
      console.log(size)
    }
  },
  data () {
    return {
      screenWidth: document.body.clientWidth,
      screenName: 'mobile',
      map: {
        src: require('~/CoverBg/web/chart002.jpg'),
        target: {
          src: require('~/target.gif')
        },
        title: {
          isShow: false
        }
      },
      targets: {
        target1: {
          isShow: false
        },
        target2: {
          isShow: false
        },
        target3: {
          isShow: false
        },
        target4: {
          isShow: false
        },
        target5: {
          isShow: false
        }
      },
      mapAnimation: {
        hints: [
          {
            id: 1,
            img: require('~/CoverBg/web/content-02.jpg')
          },
          {
            id: 2,
            img: require('~/CoverBg/web/content-03.jpg')
          },
          {
            id: 3,
            img: require('~/CoverBg/web/content-04.jpg')
          },
          {
            id: 4,
            img: require('~/CoverBg/web/content-05.jpg')
          },
          {
            id: 5,
            img: require('~/CoverBg/web/content-06.jpg')
          }
        ],
        step: 0,
        steps: {
          mobile: [
            {
              'position': 'relative',
              'top': '50%',
              'left': '50%',
              'width': '100vw',
              'height': '30vh',
              'background-position-y': 'top'
            },
            {
              'position': 'fixed',
              'top': '50%',
              'left': '50%',
              'width': '100vw',
              'height': '100vh'
            },
            {
              'position': 'fixed',
              'top': '50%',
              'left': '0',
              'transform': 'translateY(-5%)',
              'width': '100vw',
              'height': '100vh'
            },
            {
              'position': 'fixed',
              'top': '80px',
              'left': '0',
              'transform': 'translate(-5%, -5%)'
            },
            {
              'position': 'fixed',
              'top': '80px',
              'left': '0',
              'transform': 'translate(-10%, -5%)'
            },
            {
              'position': 'fixed',
              'top': '80px',
              'left': '0',
              'transform': 'translate(-60%, -15%)'
            },
            {
              'position': 'fixed',
              'top': '80px',
              'left': '0',
              'transform': 'translate(-53%, -10%)'
            },
            {
              'position': 'fixed',
              'top': '0%',
              'left': '0',
              'transform': 'translate(-50%, 0%)'
            },
            {
              'position': 'relative',
              'top': '50%',
              'left': '50%',
              'width': '100vw',
              'height': '100vh',
              'background-position-y': 'center'
            }
          ],
          pad: [
            {
              'position': 'relative',
              'top': '50%',
              'left': '50%',
              'width': '100vw',
              'height': '100vh',
              'transform': 'translate(-50%, -30%)',
              'background-position-y': 'top'
            },
            {
              'position': 'fixed',
              'top': '50%',
              'left': '50%',
              'width': '100vw',
              'height': '100vh'
            },
            {
              'position': 'fixed',
              'top': '50%',
              'left': '0',
              'transform': 'translateY(-5%)',
              'width': '100vw',
              'height': '100vh'
            },
            {
              'position': 'fixed',
              'top': '80px',
              'left': '0',
              'transform': 'translate(-5%, -15%)'
            },
            {
              'position': 'fixed',
              'top': '80px',
              'left': '0',
              'transform': 'translate(-10%, -3%)'
            },
            {
              'position': 'fixed',
              'top': '80px',
              'left': '0',
              'transform': 'translate(-62%, -14%)'
            },
            {
              'position': 'fixed',
              'top': '80px',
              'left': '0',
              'transform': 'translate(-58%, -2%)'
            },
            {
              'position': 'fixed',
              'top': '0%',
              'left': '0',
              'transform': 'translate(-52%, 5%)'
            },
            {
              'position': 'relative',
              'top': '50%',
              'left': '50%',
              'width': '100vw',
              'height': '100vh',
              'transform': 'translate(-50%, -50%)',
              'background-position-y': 'center'
            }
          ],
          table: [
            {
              'position': 'relative',
              'top': '50%',
              'left': '50%',
              'transform': 'translate(-50%, -50%)',
              'width': '80vw',
              'height': '80vh'
            },
            {
              'position': 'fixed',
              'top': '50%',
              'left': '50%',
              'transform': 'translate(-50%, -50%)',
              'width': '80vw',
              'height': '80vh'
            },
            {
              'position': 'fixed',
              'top': '50%',
              'left': '50%',
              'width': '80vw',
              'height': '80vh',
              'transform': 'translate(-50%, -50%)'
            },
            {
              'position': 'fixed',
              'top': '80px',
              'left': '0',
              'transform': 'translate(0%, -50%)'
            },
            {
              'position': 'fixed',
              'top': '80px',
              'left': '0',
              'transform': 'translate(-5%, -15%)'
            },
            {
              'position': 'fixed',
              'top': '80px',
              'left': '0',
              'transform': 'translate(-40%, -50%)'
            },
            {
              'position': 'fixed',
              'top': '80px',
              'left': '0',
              'transform': 'translate(-37%, -20%)'
            },
            {
              'position': 'fixed',
              'top': '80px',
              'left': '0',
              'transform': 'translate(-40%, -5%)'
            },
            {
              'position': 'relative',
              'top': '50%',
              'left': '50%',
              'transform': 'translate(-50%, -50%)',
              'width': '80vw',
              'height': '80vh'
            }
          ]
        }
      }
    }
  },
  mounted () {
        const vm = this
            window.onresize = () => {
                return (() => {
                    window.screenWidth = document.body.clientWidth
                    vm.screenWidth = window.screenWidth
                })()
            }

        if ( 768 <= vm.screenWidth && vm.screenWidth <= 1023 ) {
          this.screenName = 'pad'
        } else if ( 1024 < vm.screenWidth ) {
          this.screenName = 'table'
        } else {
          this.screenName = 'mobile'
        }

        window.addEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScroll: _throttle(function (e) {

      let currentHieght = window.pageYOffset

      console.log(currentHieght)
      console.log(this.$refs['animation-map'].offsetTop)
      console.log(this.$refs['animation-map'].offsetTop + this.$refs['map-start'].offsetTop)
      console.log(this.$refs['animation-map'].offsetTop + this.$refs['hints1'].offsetTop)

      let mapStart = this.$refs['animation-map'].offsetTop
      let hint1 = this.$refs['animation-map'].offsetTop + this.$refs['hints1'].offsetTop
      let hint2 = this.$refs['animation-map'].offsetTop + this.$refs['hints2'].offsetTop
      let hint3 = this.$refs['animation-map'].offsetTop + this.$refs['hints3'].offsetTop
      let hint4 = this.$refs['animation-map'].offsetTop + this.$refs['hints4'].offsetTop
      let hint5 = this.$refs['animation-map'].offsetTop + this.$refs['hints5'].offsetTop
      let mapEnd = this.$refs['animation-map'].offsetTop + this.$refs['map-end'].offsetTop
      

      if ( mapStart - 200 < currentHieght && currentHieght < mapStart ) {

        this.mapAnimation.step = 1;
        this.map.title.isShow = false
      } else if ( mapStart <= currentHieght && currentHieght < hint1 ) {

        this.mapAnimation.step = 2;
        this.targetControl()
        this.map.title.isShow = true
      } else if ( hint1 <= currentHieght && currentHieght < hint2 ) {

        this.mapAnimation.step = 3;
        this.targetControl('target1')
      } else if (  hint2 <= currentHieght && currentHieght <  hint3 ) {

        this.mapAnimation.step = 4;
        this.targetControl('target2')
      } else if (  hint3 <= currentHieght && currentHieght <  hint4 ) {

        this.mapAnimation.step = 5;
        this.targetControl('target3')
      } else if (  hint4 <= currentHieght && currentHieght <  hint5 ) {

        this.mapAnimation.step = 6;
        this.targetControl('target4')
      } else if (  hint5 <= currentHieght && currentHieght < mapEnd - 200 ) {
        this.mapAnimation.step = 7;
        this.targetControl('target5')
        this.map.title.isShow = true
      } else if (  mapEnd - 200 <= currentHieght && currentHieght < mapEnd ) {
        this.mapAnimation.step = 8;
        this.targetControl()
        this.map.title.isShow = false

      } else if (  currentHieght < mapEnd ||  mapStart - 200 < currentHieght ) {
        this.mapAnimation.step = 0;
        this.targetControl()
      }
    }, 133
    ),
    targetControl (currentTarget) {

      let targetDefault = {
        target1: {
          isShow: false
        },
        target2: {
          isShow: false
        },
        target3: {
          isShow: false
        },
        target4: {
          isShow: false
        },
        target5: {
          isShow: false
        } 
      }

      this.targets = {
        ...targetDefault
      }
      if(currentTarget) {
        this.targets[currentTarget].isShow = true
      }   
    }
  },
  destroyed () {
    window.removeEventListener('scroll', this.handleScroll)
  },
  computed: {
    handleMapStyle () {
      let current = this.mapAnimation.steps[this.screenName][this.mapAnimation.step]
      current['background-image'] = `url("${this.map.src}")`
      return {
        ...current
      } 
    }
  }
}
</script>

<style lang="scss">
$target-color: rgba(#8FC320, 1);
$target-size: 10vw;
$target-mobile-size: 85px;

.animation-map {
    background-color: inherit;
    position: relative;
    z-index: 100;
    h3 {
      transition: all 1s;
      font-weight: 900;
      background-color: rgba(0, 0, 0, 0);
    }
    .map-wrapper {
      position: relative;
      background-color: inherit;
      overflow: hidden;
      height: 100vh;
      margin: 0;
      padding: 0;
      @media screen and (min-width: 1024px) {
          height: 100vh;
      }
      .map {
        top: 100%;
        left: 50%;
        position: relative;
        transform: translateX(-50%);
        background-size: contain;
        background-repeat: no-repeat;
        z-index: 110;
        transition: all 0.5s;
        transform-origin: center;
        width: 400vw;
        height: 400vh;
        @media (min-width: 768px) and (max-width: 1023px) {
          background-size: contain;
          top: 50%;
          left: 50%;
        }
        @media screen and (min-width: 1024px) {
          width: 200vw;
          height: 200vh;
          background-size: contain;
          top: 50%;
          left: 50%;
        }
        .map-title {
          position: absolute;
          text-align: center;
          width: 100%;
          margin: 0px;
          padding: 0px;
          z-index: 120;
          top: -10%;
          left: 50%;
          font-size: 1em;
          transform: translateX(-50%);
          @media screen and (min-width: 1024px) {
            font-size: 2em;
          }
        }
        .map-title-active {
          opacity: 0;
        }
        .targets {
          border: solid 1px $target-color;
          width: $target-mobile-size;
          height: $target-mobile-size;
          border-radius: 50%;
          opacity: 0;
          .kernel {
            position: relative;
            width: 30%;
            height: 30%;
            left: 50%;
            top: 50%;
            transform: translate(-50%, -50%);
            background-color: $target-color;
            border-radius: inherit;
            box-shadow: 0 0 10px 5px $target-color;
            animation: spread 2s infinite;
          }
          @media screen and (min-width: 1024px) {
            width: $target-size;
            height: $target-size;
          }
          @keyframes spread {
              from {box-shadow: 0 0 0px 0px $target-color;}
              to {box-shadow: 0 0 7px 7px $target-color;}
          }
        }
        .isShow {
            opacity: 1;
          }
        .target1 {
          position: absolute;
          z-index: 120;
          left: 23%;
          top: 21.5%;
          @media (min-width: 768px) and (max-width: 1023px) {
            left: 24%;
            top: 27.5%;
          } 
          @media screen and (min-width: 1024px) {
            left: 23%;
            top: 73%;
          }
        }
        .target2 {
          position: absolute;
          z-index: 120;
          left: 26%;
          top: 14.5%;
          @media (min-width: 768px) and (max-width: 1023px) {
            left: 26.5%;
            top: 18.5%;
          }
          @media screen and (min-width: 1024px) {
            position: absolute;
            z-index: 120;
            left: 25.5%;
            top: 48%;
          }     
        }
        .target3 {
          position: absolute;
          z-index: 120;
          left: 64%;
          top: 22%;
          @media (min-width: 768px) and (max-width: 1023px) {
            left: 64.5%;
            top: 28.5%;
          }
          @media screen and (min-width: 1024px) {
            position: absolute;
            z-index: 120;
            left: 62%;
            top: 76%;
          }
        }
        .target4 {
          position: absolute;
          z-index: 120;
          left: 61%;
          top: 16.5%;
          @media (min-width: 768px) and (max-width: 1023px) {
            left: 61.5%;
            top: 21.5%;
          } 
          @media screen and (min-width: 1024px) {
            position: absolute;
            z-index: 120;
            left: 59.5%;
            top: 56%;
          }
        }
        .target5 {
          position: absolute;
          left: 58%;
          top: 6.5%;
          @media (min-width: 768px) and (max-width: 1023px) {
            left: 58.5%;
            top: 8%;
          }
          @media screen and (min-width: 1024px) {
            position: absolute;
            z-index: 120;
            left: 56.5%;
            top: 20%;
          }     
        }
      }
    }
    .map-hints1 {
        position: relative;
        width: 100%;
        height: 100vh;
        background-color: inherit;
        img {
          position: absolute;
          bottom: -10%;
          right: 0;
          width: 100%;
          height: auto;
          border: solid 2px white;
          border-radius: 5px;
          z-index: 120;
          @media (min-width: 768px) and (max-width: 1023px) {
            top: 50%;
            right: 10%;
            width: 50%;
          }
          @media screen and (min-width: 1024px) {
            top: 50%;
            right: 10%;
            width: 30%;
          }
        }
      }
      .map-hints2 {
        position: relative;
        width: 100%;
        height: 100vh;
        background-color: inherit;
        img {
          position: absolute;
          bottom: -10%;
          right: 0;
          width: 100%;
          height: auto;
          border: solid 2px white;
          border-radius: 5px;
          z-index: 120;
          @media (min-width: 768px) and (max-width: 1023px) {
            top: 50%;
            right: 10%;
            width: 380PX;
          }
          @media screen and (min-width: 1024px) {
            top: 50%;
            right: 10%;
            width: 30%;
          }
        }
      }
      .map-hints3 {
        position: relative;
        width: 100%;
        height: 100vh;
        background-color: inherit;
        img {
          position: absolute;
          bottom: -10%;
          right: 0;
          width: 100%;
          height: auto;
          border: solid 2px white;
          border-radius: 5px;
          z-index: 120;
          @media (min-width: 768px) and (max-width: 1023px) {
            top: 50%;
            right: 10%;
            width: 50%;
          }
          @media screen and (min-width: 1024px) {
            top: 50%;
            right: 10%;
            width: 30%;
          }
        }
      }
      .map-hints4 {
        position: relative;
        width: 100%;
        height: 100vh;
        background-color: inherit;
        img {
          position: absolute;
          bottom: -10%;
          right: 0;
          width: 100%;
          height: auto;
          border: solid 2px white;
          border-radius: 5px;
          z-index: 120;
          @media (min-width: 768px) and (max-width: 1023px) {
            top: 50%;
            right: 10%;
            width: 50%;
          }
          @media screen and (min-width: 1024px) {
            top: 50%;
            right: 10%;
            width: 30%;
          }
        }
      }
      .map-hints5 {
        position: relative;
        width: 100%;
        height: 100vh;
        background-color: inherit;
        img {
          position: absolute;
          bottom: -10%;
          right: 0;
          width: 100%;
          height: auto;
          border: solid 2px white;
          border-radius: 5px;
          z-index: 120;
          @media (min-width: 768px) and (max-width: 1023px) {
            top: 50%;
            right: 10%;
            width: 50%;
          }
          @media screen and (min-width: 1024px) {
            top: 50%;
            right: 10%;
            width: 30%;
          }
        }
      }
    }
</style>
