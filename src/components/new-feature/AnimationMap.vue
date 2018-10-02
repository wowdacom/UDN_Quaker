<template>
    <div class="animation-map" ref="animation-map">
        <h4 class="map-title" :class="{ 'map-title-active': map.title.isShow }">4個月至3歲副食品 建議一日攝取量</h4>
        <div class="map-wrapper" ref="map-start">
        <div class="map enterMap" 
            :style="handleMapStyle">
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
            :style="handleMapStyle">
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
              'transform': 'translate(-5%, -5%)',
              'width': '400vw',
              'height': '400vh'
            },
            {
              'position': 'fixed',
              'top': '80px',
              'left': '0',
              'transform': 'translate(-10%, -5%)',
              'width': '400vw',
              'height': '400vh'
            },
            {
              'position': 'fixed',
              'top': '80px',
              'left': '0',
              'transform': 'translate(-60%, -15%)',
              'width': '400vw',
              'height': '400vh'
            },
            {
              'position': 'fixed',
              'top': '80px',
              'left': '0',
              'transform': 'translate(-53%, -10%)',
              'width': '400vw',
              'height': '400vh'
            },
            {
              'position': 'fixed',
              'top': '50%',
              'left': '0',
              'transform': 'translate(-50%, -10%)',
              'width': '400vw',
              'height': '400vh'
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
              'top': '80px',
              'left': '0',
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
              'transform': 'translateX(-35%)',
              'width': '400vw',
              'height': '400vh'
            },
            {
              'position': 'fixed',
              'top': '80px',
              'left': '0',
              'transform': 'translateX(-65%)',
              'width': '400vw',
              'height': '400vh'
            },
            {
              'position': 'fixed',
              'top': '80px',
              'left': '0',
              'transform': 'translateX(-10%)',
              'width': '400vw',
              'height': '400vh'
            },
            {
              'position': 'fixed',
              'top': '80px',
              'left': '0',
              'transform': 'translateX(-25%)',
              'width': '400vw',
              'height': '400vh'
            },
            {
              'position': 'fixed',
              'top': '50%',
              'left': '0',
              'transform': 'translateY(-25%)',
              'width': '400vw',
              'height': '400vh'
            },
            {
              'position': 'static',
              'width': '100vw'
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
              'transform': 'translate(-50%, -50%)',
              'width': '80vw',
              'height': '80vh'
            },
            {
              'position': 'fixed',
              'top': '80px',
              'left': '0',
              'transform': 'translate(0%, -50%)',
              'width': '200vw',
              'height': '200vh'
            },
            {
              'position': 'fixed',
              'top': '80px',
              'left': '0',
              'transform': 'translate(-5%, -15%)',
              'width': '200vw',
              'height': '200vh'
            },
            {
              'position': 'fixed',
              'top': '80px',
              'left': '0',
              'transform': 'translate(-40%, -50%)',
              'width': '200vw',
              'height': '200vh'
            },
            {
              'position': 'fixed',
              'top': '80px',
              'left': '0',
              'transform': 'translate(-37%, -20%)',
              'width': '200vw',
              'height': '200vh'
            },
            {
              'position': 'fixed',
              'top': '80px',
              'left': '0',
              'transform': 'translate(-40%, -5%)',
              'width': '200vw',
              'height': '200vh'
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

      let mapStart = this.$refs['animation-map'].offsetTop
      let hint1 = this.$refs['animation-map'].offsetTop + this.$refs['hints1'].offsetTop
      let hint2 = this.$refs['animation-map'].offsetTop + this.$refs['hints2'].offsetTop
      let hint3 = this.$refs['animation-map'].offsetTop + this.$refs['hints3'].offsetTop
      let hint4 = this.$refs['animation-map'].offsetTop + this.$refs['hints4'].offsetTop
      let hint5 = this.$refs['animation-map'].offsetTop + this.$refs['hints5'].offsetTop
      let mapEnd = this.$refs['animation-map'].offsetTop + this.$refs['map-end'].offsetTop
      

      if ( mapStart - 200 < currentHieght && currentHieght < mapStart ) {

        this.mapAnimation.step = 1;
        this.map.title.isShow = true
      } else if ( mapStart <= currentHieght && currentHieght < hint1 ) {

        this.mapAnimation.step = 2;
        this.targetControl()
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
      } else if (  mapEnd - 200 <= currentHieght && currentHieght < mapEnd ) {
        this.mapAnimation.step = 8;
      } else if (  currentHieght < mapEnd ||  mapStart - 200 < currentHieght ) {
        this.mapAnimation.step = 0;
        this.map.title.isShow = false
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
$target-size: 85px;
$target-mobile-size: 50px;

.animation-map {
    background-color: inherit;
    position: relative;
    z-index: 100;
    h3 {
      transition: all 1s;
      font-weight: 900;
      background-color: rgba(0, 0, 0, 0);
    }
    .map-title {
      width: 100%;
      position: relative;
      text-align: center;
      margin: 0px;
      padding: 0px;
      z-index: 120;
    }
    .map-title-active {
      opacity: 0;
    }
    .map-wrapper {
      position: relative;
      background-color: inherit;
      overflow: hidden;
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
        transition: all 1s;
        transform-origin: center;
        @media (min-width: 768px) and (max-width: 1023px) {
          background-size: contain;
          top: 50%;
          left: 50%;
        }
        @media screen and (min-width: 1024px) {
          background-size: contain;
          top: 50%;
          left: 50%;
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
          top: 20.5%;
          @media screen and (min-width: 1024px) {
            left: 23%;
            top: 73%;
          }
        }
        .target2 {
          position: absolute;
          z-index: 120;
          left: 26%;
          top: 13.5%;
          @media screen and (min-width: 1024px) {
            position: absolute;
            z-index: 120;
            left: 26%;
            top: 49%;
          }     
        }
        .target3 {
          position: absolute;
          z-index: 120;
          left: 64%;
          top: 21%;
          @media screen and (min-width: 1024px) {
            position: absolute;
            z-index: 120;
            left: 63%;
            top: 76%;
          }
        }
        .target4 {
          position: absolute;
          z-index: 120;
          left: 61%;
          top: 15.5%;
          @media screen and (min-width: 1024px) {
            position: absolute;
            z-index: 120;
            left: 60%;
            top: 56%;
          }
        }
        .target5 {
          position: absolute;
          left: 58%;
          top: 5.5%;
          @media screen and (min-width: 1024px) {
            position: absolute;
            z-index: 120;
            left: 57%;
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
            width: 380PX;
            height: 100PX;
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
            height: 100PX;
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
            width: 380PX;
            height: 100PX;
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
            width: 380PX;
            height: 100PX;
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
            width: 380PX;
            height: 100PX;
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
