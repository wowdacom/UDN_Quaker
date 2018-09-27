<template>
    <div class="animation-map" ref="animation-map">
        <div class="map-wrapper" ref="map-start">
        <div class="map"
            :style="handleMapStyle">
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
        <div class="map"
            :style="handleMapStyle">
        </div>
        </div>
    </div>  
</template>

<script>

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
        src: require('~/CoverBg/web/chart002.jpg')
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
              'position': 'static',
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
              'transform': 'translateX(-15%)',
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
          pad: {

          },
          table: [
            {
              'position': 'static',
              'top': '80px',
              'left': '0',
              'width': '100vw',
              'height': '100vh'
            },
            {
              'position': 'fixed',
              'top': '50px',
              'left': '0',
              'width': '100vw',
              'height': '100vh'
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
              'transform': 'translate(-40%, -20%)',
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
    handleScroll () {

      let currentHieght = window.pageYOffset

      let mapEnd = this.$refs['animation-map'].offsetTop + this.$refs['map-end'].offsetTop
      let step0 = this.$refs['animation-map'].offsetTop
      let step1 = this.$refs['animation-map'].offsetTop + this.$refs['hints1'].offsetTop
      let step2 = this.$refs['animation-map'].offsetTop + this.$refs['hints2'].offsetTop
      let step3 = this.$refs['animation-map'].offsetTop + this.$refs['hints3'].offsetTop
      let step4 = this.$refs['animation-map'].offsetTop + this.$refs['hints4'].offsetTop
      let step5 = this.$refs['animation-map'].offsetTop + this.$refs['hints5'].offsetTop
      let step6 = this.$refs['animation-map'].offsetTop + this.$refs['hints5'].offsetHeight

      console.log(mapEnd)
      
      if ( step0 - 200 < currentHieght && currentHieght < step0 ) {
        console.log(1)
        this.mapAnimation.step = 1;
      } else if ( step0 < currentHieght && currentHieght < step1 ) {
        this.mapAnimation.step = 2;
      } else if ( step1 < currentHieght && currentHieght < step2 ) {
        this.mapAnimation.step = 3;
      } else if (  step2 < currentHieght && currentHieght <  step3 ) {
        this.mapAnimation.step = 4;
      } else if (  step3 < currentHieght && currentHieght <  step4 ) {
        this.mapAnimation.step = 5;
        console.log(5)
      } else if (  step4 < currentHieght && currentHieght <  step5 ) {
        this.mapAnimation.step = 6;
        console.log(6)
      } else if (  step5 < currentHieght && currentHieght < mapEnd ) {
        this.mapAnimation.step = 1;
      } else if (  step5 < currentHieght && currentHieght < mapEnd ) {
        this.mapAnimation.step = 1;
      } else {
        this.mapAnimation.step = 0;
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
.animation-map {
    position: relative;
    width: 100%;
    z-index: 100;
    .map-wrapper {
      position: relative;
      height: 100vh;
      background-color: white;
      overflow: hidden;
      .map {
        position: relative;
        top: 50%;
        height: 100%;
        background: white;
        background-size: contain;
        background-repeat: no-repeat;
        z-index: 110;
        transition: all 0.5s;
        @media screen and (min-width: 1024px) {
          background-position: center;
        }   
      }
    }
    .map-hints1 {
        position: relative;
        width: 100%;
        height: 100vh;
        background-color: white;
        img {
          position: absolute;
          top: 50%;
          right: 0;
          width: 100%;
          height: 100px;
          border: solid 5px salmon;
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
            height: 30%;
          }
        }
      }
      .map-hints2 {
        position: relative;
        width: 100%;
        height: 100vh;
        background-color: white;
        img {
          position: absolute;
          top: 50%;
          right: 0;
          width: 100%;
          height: 250px;
          border: solid 5px salmon;
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
            height: 30%;
          }
        }
      }
      .map-hints3 {
        position: relative;
        width: 100%;
        height: 100vh;
        background-color: white;
        img {
          position: absolute;
          top: 50%;
          right: 0;
          width: 100%;
          height: 250px;
          border: solid 5px salmon;
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
            height: 30%;
          }
        }
      }
      .map-hints4 {
        position: relative;
        width: 100%;
        height: 100vh;
        background-color: white;
        img {
          position: absolute;
          top: 50%;
          right: 0;
          width: 100%;
          height: 250px;
          border: solid 5px salmon;
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
            height: 30%;
          }
        }
      }
      .map-hints5 {
        position: relative;
        width: 100%;
        height: 100vh;
        background-color: white;
        img {
          position: absolute;
          top: 50%;
          right: 0;
          width: 100%;
          height: 250px;
          border: solid 5px salmon;
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
            height: 30%;
          }
        }
      }
    }
</style>
