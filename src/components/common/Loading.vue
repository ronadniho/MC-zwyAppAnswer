<template>
  <div class="container">
    <div class="content flex">
      <!--<ul class="animate clr">
        <li class="lt"></li>
        <li class="lt"></li>
        <li class="lt"></li>
        <li class="lt"></li>
        <li class="lt"></li>
      </ul>-->
      <main class="" id="loaded">
        <div class="loaders">
          <div class="loader">
            <div class="loader-inner line-scale">
              <div></div>
              <div></div>
              <div></div>
              <div></div>
              <div></div>
            </div>
          </div>
        </div>
      </main>
      <div class="tips">加载中...</div>
    </div>
  </div>

</template>

<script>

  export default {
    name: 'Loading',
    props: [],
    data() {
      return {}
    },
    created: function () {
      document.addEventListener('DOMContentLoaded', function () {
        document.querySelector('main').className += 'loaded';
      });
    },
    methods: {}
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
  @import '../../variable';

  /*
    @keyframes mymove1 {
      0% {
        padding: 35px 0;
        background-color: #ff6666;
      }
      50% {
        padding: 20px 0;
      }
      100% {
        padding: 35px 0;
      }
    }
  */
  @-webkit-keyframes line-scale {
    0% {
      -webkit-transform: scaley(1);
      transform: scaley(1);
    }

    50% {
      -webkit-transform: scaley(0.4);
      transform: scaley(0.4);
    }

    100% {
      -webkit-transform: scaley(1);
      transform: scaley(1);
    }
  }

  @keyframes line-scale {
    0% {
      -webkit-transform: scaley(1);
      transform: scaley(1);
    }

    50% {
      -webkit-transform: scaley(0.4);
      transform: scaley(0.4);
    }

    100% {
      -webkit-transform: scaley(1);
      transform: scaley(1);
    }
  }

  .line-scale > div:nth-child(1) {
    -webkit-animation: line-scale 1s 0.1s infinite cubic-bezier(.2, .68, .18, 1.08);
    animation: line-scale 1s 0.1s infinite cubic-bezier(.2, .68, .18, 1.08);
  }

  .line-scale > div:nth-child(2) {
    -webkit-animation: line-scale 1s 0.2s infinite cubic-bezier(.2, .68, .18, 1.08);
    animation: line-scale 1s 0.2s infinite cubic-bezier(.2, .68, .18, 1.08);
  }

  .line-scale > div:nth-child(3) {
    -webkit-animation: line-scale 1s 0.3s infinite cubic-bezier(.2, .68, .18, 1.08);
    animation: line-scale 1s 0.3s infinite cubic-bezier(.2, .68, .18, 1.08);
  }

  .line-scale > div:nth-child(4) {
    -webkit-animation: line-scale 1s 0.4s infinite cubic-bezier(.2, .68, .18, 1.08);
    animation: line-scale 1s 0.4s infinite cubic-bezier(.2, .68, .18, 1.08);
  }

  .line-scale > div:nth-child(5) {
    -webkit-animation: line-scale 1s 0.5s infinite cubic-bezier(.2, .68, .18, 1.08);
    animation: line-scale 1s 0.5s infinite cubic-bezier(.2, .68, .18, 1.08);
  }

  .loader-inner {
    text-align: center;
  }

  .line-scale > div {
    background-color: @theme;
    width: 8px;
    height: 47px;
    border-radius: 4px;
    margin: 2px;
    -webkit-animation-fill-mode: both;
    animation-fill-mode: both;
    display: inline-block;
  }

  .container {
    position: fixed;
    left: 0;
    top: 0;
    bottom: 0;
    right: 0;
    background-color: rgba(255, 255, 255 ,0);
    z-index: 2000;
    height: @max;
    .content {
      flex-flow: column nowrap;
      position: absolute;
      top: 50%;
      left: 50%;
      margin-top: -67px;
      margin-left: -84px;
      width: 168px;
      height: 134px;
      background-color: #e6e6e6;
      border-radius: 8px; /*no*/
      .loaded, #loaded {
        flex-grow: 2;
        display: flex;
        align-items: center;
        justify-content: center;
      }
      .animate {
        width: 200px;
        background-color: @white;
        height: 90px;
        position: relative;
        li {
          position: absolute;
          top: 50%;
          margin-top: -35px;
          background-color: @theme;
          width: 8px; /*no*/
          max-height: 70px;
          min-height: 40px;
          border-radius: 5px;

        }
      }
      .tips {
        flex-grow: 1;
        text-align: center;
        color: #444;
        font-weight: 600;
        font-size: 31px;
      }
    }

  }
</style>
