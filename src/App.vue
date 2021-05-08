<template>
    <v-main>
      <div class="slide1">
          <div class="picture-and-intro" ref="logoText">
              <img ref="logoImg" src="./assets/MBIcon.svg" class="logo">
              <div class="header">
                  <div class="name">Markus Böbel</div>
                  <div class="study">M.Sc. Information System</div>
              </div>
              <div ref="inWork" class="inwork">
                  This page is still in work
              </div>
          </div>
      </div >
    <div class="slide2">

    </div >
    </v-main>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  name: "App",
  components: {
  },
  methods: {
    handleScroll: function(event: Event) {
        // console.log(window.scrollY - this.oldScroll);

        // this.$refs.logoText.style.top += (0.01 * (window.scrollY - this.oldScroll)) + "px";
        this.oldScroll = window.scrollY;

        const percentageOfMovement: number = window.scrollY / window.innerHeight;
        console.log(percentageOfMovement);
        if (this.$refs.logoImg) {
            (this.$refs.logoImg as HTMLElement).style.width = (((1-percentageOfMovement)*25)+25)+"%";
            (this.$refs.logoImg as HTMLElement).style.top = (((1-percentageOfMovement)*100)+100)+"px";
        }
        if (this.$refs.inWork) {
            (this.$refs.inWork as HTMLElement).style.fontSize = (percentageOfMovement+1)+"em";
        }
    }
  },
  created() {
      window.addEventListener('scroll', this.handleScroll);

  },
  data: () => ({
    oldScroll: 0,

  })
});
</script>
<style lang="scss">
      @import "variables";

      html, body {
          font-family: "Roboto Mono", monospace;
      }
      .slide1 {
          width: 100vw;
          height: 100vh;

          display: flex;
          justify-content: center;
          align-items: center;
      }
      .name {
          font-family: Roboto Mono, monospace;
          font-style: normal;
          font-weight: 300;
          font-size: 2em;
          line-height: 76px;
      }
      .study{
          font-family: Roboto Mono, monospace;
          font-style: normal;
          font-weight: 100;
          font-size: 1.2em;

      }
      .logo{
          width: 50%;
      }
      .picture-and-intro {
          position: fixed;
          display: flex;
          align-items: center;

          flex-direction: column;
      }
      .inwork{

      }
      .picture-and-intro > * {
          padding: 1em;
      }
      .picture-and-intro * {
          text-align: center;
      }
      .slide2 {
          background-color: khaki;
          height: 100vh;
      }

</style>
