<template>
  <div v-bind:style="styles" class="spinner spinner--socker">
    <div v-bind:style="innerStyles" class="spinner-inner">
      <div class="cube panelLoad">
        <div class='cube-face cube-face-front'>M</div>
        <div class='cube-face cube-face-back'>O</div>
        <div class='cube-face cube-face-left'>S</div>
        <div class='cube-face cube-face-right'>T</div>
        <div class='cube-face cube-face-bottom'>A</div>
        <div class='cube-face cube-face-top'>F</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    size: {
      default: '120px'
    }
  },
  computed: {
    innerStyles () {
      let size = parseInt(this.size) / 2
      return {
        transform: 'scale(' + (size / 75) + ')'
      }
    },
    styles () {
      return {
        width: this.size,
        height: this.size
      }
    }
  }
}
</script>

<style lang="scss" scoped>
  .spinner{
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: center;
    * {
      box-sizing: border-box;
    }
  }
  .cube {
    width: 80px;
    height: 80px;
    line-height: 80px;
    text-align: center;
    transform-style: preserve-3d;
    transition: transform 0.5s 0.1s;
    perspective: 9999px;
    color: #333;
    opacity: 1;
    position: relative;
    &.panelLoad {
      z-index: 11;
      top: 50%;
      animation: letter-cube-panel 3.2s infinite    ;
      .cube-face {
        font-family: "Open Sans",sans-serif;
        font-size: 50px;
        color: #1C2541;
        box-shadow: inset 0 0 0 1px #1C2541, 0 0 1px 1px #1C2541;
      }
    }
    .cube-face {
      width: inherit;
      height: inherit;
      position: absolute;
      background: white;
      box-shadow: inset 0 0 0 1px #333, 0 0 1px 1px #333;
      opacity: 1;
    }
    .cube-face-front {
      transform: translate3d(0, 0, 40px);
      font-size: 57px;
    }
    .cube-face-back {
      transform: rotateY(180deg) translate3d(0, 0, 40px);
    }
    .cube-face-left {
      transform: rotateY(-90deg) translate3d(0, 0, 40px);
    }
    .cube-face-right {
      transform: rotateY(90deg) translate3d(0, 0, 40px);
    }
    .cube-face-top {
      transform: rotateX(90deg) translate3d(0, 0, 40px);
    }
    .cube-face-bottom {
      transform: rotateX(-90deg) translate3d(0, 0, 40px);
    }
  }
  @keyframes letter-cube-panel {
    0% {
      transform: rotateY(0deg);
    }
    15% {
      transform: rotateY(180deg);
    }
    30% {
      transform: rotateY(90deg);
    }
    45% {
      transform: rotateY(270deg);
    }
    60% {
      transform: rotateX(90deg) 
    }
    75% {
      transform: rotateX(-90deg) 
    }
    90% {
      transform: rotateX(90deg) 
    }
  }
</style>