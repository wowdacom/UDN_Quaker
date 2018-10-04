<template>
    <div class="animation-map" ref="animation-map">
        <div class="extra-wrapper"  ref="map-start">
          <div class="map-wrapper" :style="animationMapStep[step]" >
            <img :src="map.src" :style="animationTargetStep[screenName][step]" class="map">
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
        <div class="extra-wrapper"  ref="map-end">
          <div class="map-wrapper" :style="animationMapStep[step]">
            <img :src="map.src" :style="animationTargetStep[screenName][step]" class="map">
            <img class="target" :class="{ 'isShow': targets.target1.isShow }" :style="animationTargetStep[screenName][step]" :src="require('~/CoverBg/web/point01.png')" alt="">
            <img class="target" :class="{ 'isShow': targets.target2.isShow }" :style="animationTargetStep[screenName][step]" :src="require('~/CoverBg/web/point02.png')" alt="">
            <img class="target" :class="{ 'isShow': targets.target3.isShow }" :style="animationTargetStep[screenName][step]" :src="require('~/CoverBg/web/point03.png')" alt="">
            <img class="target" :class="{ 'isShow': targets.target4.isShow }" :style="animationTargetStep[screenName][step]" :src="require('~/CoverBg/web/point04.png')" alt="">
            <img class="target" :class="{ 'isShow': targets.target5.isShow }" :style="animationTargetStep[screenName][step]" :src="require('~/CoverBg/web/point05.png')" alt="">
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
      animationMapStep: [
        {
          'position': 'relative',
          'top': '0',
          'left': '0',
          // 'transform': 'translateX(-25%)'
        },
        {
          'position': 'fixed',
          'top': '0'
        },
        {
          'position': 'fixed',
          'top': '0'
        },
        {
          'position': 'fixed',
          'top': '0'
        },
        {
          'position': 'fixed',
          'top': '0'
        },
        {
          'position': 'fixed',
          'top': '0'
        },
        {
          'position': 'fixed',
          'top': '0'
        },
        {
          'position': 'fixed',
          'top': '0'
        }
      ],
      animationTargetStep: {
        'table': [
        {
          'position': 'absolute',
          'transform': 'scale(0.5)',
          
        },
        {
          'position': 'absolute',
          'transform': 'translate(0%, 0%) scale(.5)',
          'top': '0%'
        },
        {
          'position': 'absolute',
          'transform': 'translate(0%, -50%) scale(1)',
        },
        {
          'position': 'absolute',
          'transform': 'translate(-5%, -25%) scale(1)',
        },
        {
          'position': 'absolute',
          'transform': 'translate(-50%, -50%) scale(1)',
        },
        {
          'position': 'absolute',
          'transform': 'translate(-50%, -25%) scale(1)',
        },
        {
          'position': 'absolute',
          'transform': 'translate(-40%, -2%) scale(1)',
        },
        {
          'position': 'absolute',
          'transform': 'translate(0%, 0%) scale(.5)',
        }
      ],
        'pad': [
        {
          'position': 'absolute',
          'transform': 'scale(0.5)',
          'top': '50%'     
        },
        {
          'position': 'absolute',
          'transform': 'translate(0%, 50%) scale(.5)',
        },
        {
          'position': 'absolute',
          'transform': 'translate(-10%, -45%) scale(2)',
        },
        {
          'position': 'absolute',
          'transform': 'translate(-25%, -15%) scale(2)',
        },
        {
          'position': 'absolute',
          'transform': 'translate(-125%, -50%) scale(2)',
        },
        {
          'position': 'absolute',
          'transform': 'translate(-115%, -30%) scale(2)',
        },
        {
          'position': 'absolute',
          'transform': 'translate(-100%, 0%) scale(2)',
        },
        {
          'position': 'absolute',
          'transform': 'translate(-100%, 0%)',
          'transform': 'scale(.5)',
        }
      ],
        'mobile': [
          {
          'position': 'absolute',
          'top': '50%',
          'transform': 'scale(0.5)'
          },
          {
            'position': 'absolute',
            'transform': 'translate(0%, 50%) scale(.5)',
          },
          {
            'position': 'absolute',
            'transform': 'translate(-20%, -90%) scale(2.5)',
          },
          {
            'position': 'absolute',
            'transform': 'translate(-30%, -30%) scale(2.5)',
          },
          {
            'position': 'absolute',
            'transform': 'translate(-160%, -120%) scale(2.5)',
          },
          {
            'position': 'absolute',
            'transform': 'translate(-130%, -80%) scale(2.5)',
          },
          {
            'position': 'absolute',
            'transform': 'translate(-120%, 0%) scale(2.5)',
          },
          {
            'position': 'absolute',
            'transform': 'translate(0%, 0%) scale(.5)',
          }
        ]
      },
      step: 0,
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
        step: 0
      }
    }
  },
  mounted () {
    this.handleResize()
    window.addEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleResize () {
      const vm = this
      window.onresize = () => {
          return (() => {
              window.screenWidth = document.body.clientWidth
              vm.screenWidth = window.screenWidth
          })()
      }
      
      if ( 768 <= vm.screenWidth && vm.screenWidth <= 1023 ) {
        vm.screenName = 'pad'
      } else if ( 1024 < vm.screenWidth ) {
        vm.screenName = 'table'
      } else {
        vm.screenName = 'mobile'
      }
      
    },
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

        this.step = 1
        this.mapAnimation.step = 1;
        this.map.title.isShow = false
      } else if ( mapStart <= currentHieght && currentHieght < hint1 ) {

        
        this.mapAnimation.step = 2;
        this.targetControl()
        this.map.title.isShow = true
      } else if ( hint1 <= currentHieght && currentHieght < hint2 ) {

        this.step = 2;
        this.mapAnimation.step = 3;
        this.targetControl('target1')
      } else if (  hint2 <= currentHieght && currentHieght <  hint3 ) {

        this.step = 3;
        this.mapAnimation.step = 4;
        this.targetControl('target2')
      } else if (  hint3 <= currentHieght && currentHieght <  hint4 ) {

        this.step = 4;
        this.mapAnimation.step = 5;
        this.targetControl('target3')
      } else if (  hint4 <= currentHieght && currentHieght <  hint5 ) {
        this.step = 5;
        this.mapAnimation.step = 6;
        this.targetControl('target4')
      } else if (  hint5 <= currentHieght && currentHieght < mapEnd - 200 ) {

        this.step = 6;
        this.mapAnimation.step = 7;
        this.targetControl('target5')
        this.map.title.isShow = true
      } else if (  mapEnd - 200 <= currentHieght && currentHieght < mapEnd ) {

        this.step = 7;
        this.mapAnimation.step = 8;
        this.targetControl()
        this.map.title.isShow = false

      } else if (  currentHieght < mapEnd ||  mapStart - 200 < currentHieght ) {
        this.step = 0
        this.mapAnimation.step = 0;
        this.targetControl()
      } else {
        this.step = 0
      }
    }, 133
    ),
    targetControl (currentTarget) {

      console.log("its work");
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
    .extra-wrapper {
      width: 100vw;
      height: 100vh;
      .map-wrapper {
        width: 100vw;
        height: 100vh;
        overflow: hidden;
        transition: all 0.5s;
        .map {
          width: 200%;
          height: auto;
          position: absolute;
          top: 0;
          left: 0;
          z-index: 120;
          transform-origin: top left;
          transform: translateY(-50%);
          transition: all 1s;
        }
        .target {
          width: 200%;
          height: auto;
          position: absolute;
          top: 0;
          left: 0;
          z-index: 130;
          transform: translateY(-50%);
          transform-origin: left top;
          transition: all 1s;
          animation: flash 1s infinite alternate;
          visibility:hidden;
        }

        .isShow {
          visibility: visible;
        }
        @keyframes flash {
          from {opacity: 0;}
          to {opacity: 1;}
        }
      }
    }

    //提示字
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
